i use yarn before hahaha

support tutorial from : (video link)[https://www.youtube.com/watch?v=GV-D85D9KJQ&t=1824s&ab_channel=MakeAppswithDanny]

---

#### quasar dev -m electron

When you run this command, Quasar will launch your application using Electron, allowing you to develop and test your Quasar-based desktop application.

### quasar build -m electron

As of my last update in September 2021, the command "quasar build -m electron" is used in Quasar Framework to build your application for Electron. This command bundles your Quasar-based web application into an Electron desktop application package, allowing you to distribute it as a standalone desktop app for different platforms (Windows, macOS, Linux).

---

### quasar build -m capacitor -T [android]

---

cordova or electron for cli quasar?

Choosing between Cordova and Electron for a Quasar CLI project depends on the target platform and the type of application you want to build. Both Cordova and Electron are powerful tools, but they serve different purposes:

Cordova:
Cordova is a platform that allows you to build mobile applications using web technologies (HTML, CSS, and JavaScript). It packages your web application into a native container and provides access to device features through plugins. This allows you to create cross-platform mobile apps for iOS and Android using a single codebase.

Use Cordova with Quasar if you want to build mobile apps that can be distributed through app stores or installed on users' devices. It is suitable for building applications that require native device features, such as camera access, geolocation, and push notifications.

To use Cordova with Quasar, you can use the "quasar mode add cordova" command to add Cordova integration to your project.

Electron:
Electron, on the other hand, is a framework for building desktop applications using web technologies. It allows you to package your web application as a standalone desktop application for Windows, macOS, and Linux. Electron applications run as native desktop apps and have access to operating system features.

Use Electron with Quasar if you want to create cross-platform desktop applications that can be distributed independently, similar to traditional desktop software.

To use Electron with Quasar, you can use the "quasar mode add electron" command to add Electron integration to your project.

In summary, if you want to build mobile applications, choose Cordova integration with Quasar. If you want to build desktop applications, choose Electron integration with Quasar. It's worth noting that you can even use both Cordova and Electron in the same Quasar project if you need to support both mobile and desktop platforms.

Before deciding, consider the specific requirements of your project and the target platforms to ensure you choose the right integration that meets your application's needs.

---

# Make Simple Aplication convert to ANDROID and WEBSITE

## consume API

# Quasar App (quasar-todo)

A Quasar Project

## Install the dependencies

```bash
yarn
# or
npm install
```

### Start the app in development mode (hot-code reloading, error reporting, etc.)

```bash
quasar dev
```

### Lint the files

```bash
yarn lint
# or
npm run lint
```

### Format the files

```bash
yarn format
# or
npm run format
```

### Build the app for production

```bash
quasar build
```

### Customize the configuration

See [Configuring quasar.config.js](https://v2.quasar.dev/quasar-cli-vite/quasar-config-js).
