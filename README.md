# LineageOS for Redmi Note 11 / NFC (spes)

This is a modern, responsive landing page designed to host downloads, changelogs, installation guides, and screenshots for custom Android ROM releases, specifically made for LineageOS on the Redmi Note 11 (codenamed "spes").

The entirely static frontend uses HTML, CSS, and Vanilla JavaScript. It is designed around a central `CONFIG` object, making it incredibly easy for ROM maintainers to update content quickly without repeatedly editing layout or logic simply by modifying the configuration values.

## Key Features

*   **Centralized Configuration:** All text, links, versions, and lists can be updated inside a single JavaScript `CONFIG` object.
*   **Modern Responsive UI:** Features a sleek dark mode theme with glassmorphism elements, gradient text, and dynamic micro-animations suitable for desktop, tablet, and mobile viewing.
*   **Downloads Management:** Neatly organizes ROM versions with their sizes, android versions, and upload dates, clearly highlighting the latest release. Includes a prominent download confirmation popup.
*   **Built-in Markdown Parser:** Write out your changelogs and installation guides in standard markdown right in the configuration block. The page will automatically parse and render headings, lists, bold text, and code blocks.
*   **Interactive Image Gallery:** Built-in lightbox module to display device screenshots seamlessly without redirecting the user.
*   **Direct Sharing Mode:** Changelogs and installation guides support "Shared View Mode," allowing maintainers to copy a direct link to the guide (e.g., `#view-changelog`) which displays a focused, modal-like view to the receiver.
*   **Dynamic Warnings & Notes:** An alert system to bring crucial information (like flashing precautions) to the user's immediate attention.

## Project Structure

*   \`index.html\`: The core application file containing all layout, styling, and logic.
*   \`src/\`: Directory containing static media assets.
    *   \`favicon.png\`: Site icon.
    *   \`lineage-logo.png\`: Navbar brand logo.
    *   \`model.png\`: The floating device mockup shown in the hero section.
    *   \`owner.svg\`: Maintainer avatar footprint.
    *   \`screenshots/\`: Directory to store the device feature screenshots referenced in the `CONFIG`.

## How to Configure and Update

To update the content of the landing page for newer builds, open \`index.html\` in any text editor and scroll down to the \`<script>\` section at the bottom to locate the \`CONFIG\` object.

### The Configuration Object

1.  **Basic Details**
    Modify the \`rom\`, \`device\`, \`status\`, and \`description\` properties to match the current identity and tagline of your release.

2.  **Maintainer Details**
    Update the \`maintainer\` object with your alias, role, avatar relative path, and any relevant social links (e.g., Telegram, GitHub, XDA).

3.  **Screenshots List**
    Ensure your screenshots are placed into the \`src/screenshots/\` directory. List their exact filenames in the \`screenshots\` array. They will be alphabetized automatically.

4.  **Downloads Configuration**
    Add new releases to the top of the \`downloads\` array to mark them as the "Latest". Each object takes:
    *   \`rom_version\`: ROM Version (e.g. 1.3).
    *   \`android_version\`: Associated OS layer (e.g. 16).
    *   \`size\`: The package size (e.g. 840 MB).
    *   \`date\`: Upload date context.
    *   \`download_link\`: URL to the OTA ZIP or hosting mirror.

5.  **Notices and Precautions**
    Add relevant flashing advice to the \`notes\` array. They accept a \`type\` of either \`info\` (blue) or \`warning\` (yellow).

6.  **Support Directives**
    Link official community support hubs within the \`support\` array, giving a label, description, and target URL.

7.  **Guides (Changelog & Install)**
    Write out the change history and flashing steps in the respective \`changelog\` and \`install\` markdown template literals.

## Requirements and Dependencies

This project is entirely zero-dependency. Everything is encapsulated inside the `index.html` file using standard web APIs. No build steps (like Webpack, Node.js, or NPM) are required. Simply host the root folder containing the index file and the `src` assets on any basic HTTP server, GitHub Pages, or any static site provider.

## License

This project is distributed as open-source code. Use it, adopt it for your own custom device builds, and customize the styles as needed. Ensure standard LineageOS licensing applies regarding their logos and trademarks.
