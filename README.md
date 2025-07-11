# 🏠 Home Assistant Blueprints by Michael Bieri

This repository contains **custom blueprints and automations** for [Home Assistant](https://www.home-assistant.io/), created and maintained by [@proBieri](https://github.com/proBieri).

These blueprints aim to simplify your smart home automation by providing ready-to-use templates that can be imported and customized directly in Home Assistant.


## 🚀 Getting Started

### 🔽 1. Download a Blueprint

You can either clone the repository or download only the blueprints you need.

```bash
git clone https://github.com/proBieri/HomeAssistant.git
```

### 📥 2. Import into Home Assistant

1. In Home Assistant, go to **Settings → Automations & Scenes → Blueprints**.
2. Click on **Import Blueprint**.
3. Paste the raw GitHub URL of the blueprint YAML file (e.g. `https://raw.githubusercontent.com/proBieri/HomeAssistant/main/blueprints/automation/probieri/<your-blueprint>.yaml`).
4. Click **Preview**, then **Import Blueprint**.

### ⚙️ 3. Create an Automation

After importing, go to **Automations** and click **Add Automation → Start with a Blueprint**. Select your imported blueprint and customize it as needed.

---

## 📦 Available Blueprints

| Name                                 | Description                                                         |
|--------------------------------------|---------------------------------------------------------------------|
| generic_microinverter_regulator.yaml | Optimize power limit for microinverters with multiple mppt trackers |

> *Feel free to contribute improvements or request new blueprints!*

---

## ✅ Requirements

- A working [Home Assistant](https://www.home-assistant.io/installation/) setup (Core, OS, Supervised, or Container)
- Integration-specific dependencies (if a blueprint uses entities from other integrations)

---

## 👨‍💻 Contributing

Pull requests are welcome!

1. Fork the repository.
2. Create your feature branch: `git checkout -b my-feature`.
3. Commit your changes: `git commit -am 'Add my new blueprint'`.
4. Push to the branch: `git push origin my-feature`.
5. Open a pull request.

---

## ☕ Support My Work

If you find these blueprints helpful and want to support further development, consider buying me a coffee:

[![Buy Me a Coffee](https://img.shields.io/badge/-Buy%20me%20a%20coffee-%23ffdd00?style=flat-square&logo=buy-me-a-coffee&logoColor=black)](https://buymeacoffee.com/probieri)

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## 🙌 Acknowledgements

Thanks to the amazing Home Assistant community for continuous inspiration and support!
