# Dynamic Microinverter Regulator/Limiter

## 🔧 Description

This Home Assistant automation blueprint dynamically regulates the **AC power limit** of a microinverter, based on:

- 📈 Target AC output  
- ⚡ Current AC output  
- 🔌 DC input per channel (detects if individual channels are curtailed to ≥96%)

The automation **raises the AC limit** if power is below the target and at least one DC input is curtailed, or **lowers the limit** when full output is reached and no channels are curtailed. A **hysteresis** prevents frequent adjustments due to small fluctuations.

## 🧠 Ideal Use Case

Perfect for **microinverters** with **multiple MPPT inputs**, such as Hoymiles (e.g., HM-600, HM-1500), to optimize power output under dynamic generation conditions like shading or partial loads.

---

## ⚙️ Inputs

| Input                  | Description                                           |
|------------------------|-------------------------------------------------------|
| `ac_output`            | Sensor for current inverter AC power [W]             |
| `inverter_ac_limit`    | Number entity for setting the inverter limit [W]     |
| `dc_channels`          | List of sensors for DC input power per channel [W]   |
| `target_ac_output`     | Input number to define the desired AC output [W]     |
| `range_min`            | Minimum allowed AC limit [W]                          |
| `range_max`            | Maximum allowed AC limit [W]                          |
| `hysteresis`           | Minimum delta before changes are applied [W]         |
| `timer_entity`         | Timer entity to delay re-adjustment after changes    |

---

## 📐 Logic Summary

1. Calculate real-time **efficiency** from DC/AC ratio.
2. Detect **channel curtailment** (≥96% of per-channel DC limit).
3. If curtailment exists and output is below target → raise limit.
4. If no curtailment and output is at or above target → lower limit.
5. Avoid regulation if:
   - AC is below 25% of minimum range
   - Timer is running
   - Change is smaller than hysteresis

---

## 📝 Example Log Entry

```
Microinverter regulator:
New limit set: 580 W
(actual ac output: 530 W, target AC output: 600 W, delta: 70 W, new_value: 585 W,
DC power: 610 W, Efficiency: 86.9%)
```

---

## 🧪 Review

This blueprint is:

✅ **Flexible** – Accepts any number of DC input sensors  
✅ **Efficient** – Avoids overreacting thanks to hysteresis and a delay timer  
✅ **Smart** – Uses real-time efficiency calculation and curtailment detection  
✅ **Well-suited** – Designed with real-world microinverter behavior in mind  
⚠️ **Note** – Requires that the inverter responds to changes in a `number` entity for AC limit (some integrations may not support this natively)
