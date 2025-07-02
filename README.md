# Betaflight Web Configurator

A modern, web-based interface for connecting to and configuring Betaflight flight controllers. This application leverages the **Web Serial API** to communicate directly with your drone's hardware from a compatible browser, eliminating the need for native software.

It allows you to manage multiple quadcopter profiles, automatically sync and parse key configuration details, and interact with the Betaflight Command Line Interface (CLI) in a polished, "Matrix-themed" environment.

![Screenshot of the Betaflight Web Configurator](https://storage.googleapis.com/agentops-images/webapp-screenshot.png)

## Features

- **Web Serial Connection:** Connect directly to your flight controller without installing any software.
- **Profile Management:**
  - Create, edit, and delete distinct profiles for each of your quadcopters.
  - Assign a name, description, and a custom image to each profile.
- **Automated Sync & Parsing:**
  - A single "Sync from FC" button fetches the `version`, `diff all`, and `dump all` configurations.
  - Automatically parses the output to display key details like:
    - Firmware Version
    - Board Name
    - Manufacturer
    - MCU
    - Craft Name
    - ESC Protocol
- **CLI Interface:**
  - Full access to the Betaflight CLI for sending custom commands.
  - View saved `version`, `dump`, and `diff` configurations for any profile at any time.
- **Firebase Backend:**
  - Uses Firebase for anonymous user authentication and Firestore to save all profiles and configurations, so your data persists between sessions.
- **Themed UI:** A polished and responsive "Matrix green" user interface.

## How to Use

1.  **Open the Application:**
    - Open the `index.html` file in a web browser that supports the Web Serial API (e.g., Google Chrome, Microsoft Edge).

2.  **Connect to the Flight Controller:**
    - Plug your flight controller into your computer via a USB cable.
    - Click the **Connect** button in the top-right corner of the application.
    - A browser pop-up will appear. Select the correct serial port for your flight controller and click "Connect".
    - The CLI Interface will display a confirmation message once the connection is established.

3.  **Create a Profile:**
    - Click the **+ Add New Profile** button.
    - In the modal window, provide a name, a description, and optionally upload an image for your quadcopter.
    - Click **Save Profile**.

4.  **Sync from the Flight Controller:**
    - Select the newly created profile from the list on the left.
    - Click the **Sync from FC** button.
    - The application will automatically run the necessary commands, save the output, and populate the "Flight Controller Details" card with the parsed information.

5.  **View Configuration & Use the CLI:**
    - The parsed details (Firmware, Board, etc.) are now visible in the profile card.
    - In the "Saved Configuration" card, you can click **Version**, **Dump**, or **Diff** to view the raw output that was saved during the sync.
    - You can also send manual commands using the input field at the bottom of the "CLI Interface" card.

## Technology Stack

- **Frontend:** HTML5, Tailwind CSS, Vanilla JavaScript (ESM)
- **Backend:** Firebase (Authentication and Firestore)
- **Communication:** Web Serial API
- **Icons:** Font Awesome
