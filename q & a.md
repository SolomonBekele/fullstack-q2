## Questions

1. What core protocols does ETChat use to ensure real-time, secure communication and device synchronization?
2. How does XMPP synchronize messages, call logs, and presence status across multiple devices in ETChat?
3. Which primary client-side library manages XMPP communication in the browser for ETChat, and what are its key features?
4. For voice and video calls in ETChat, what is the role of @comera/comera-protocol-bindings and how many active participants can a call support?
5. What is the development workflow for ETChat regarding local setup, build, and serve scripts?
6. How does the ETChat application enable Progressive Web App (PWA) features for its users?
7. What best practices are recommended for handling sensitive data within environment configuration files like .env?
8. What are two major security limitations of the robots.txt file as mentioned in the documentation?
9. What is the main purpose of the webpack.common.ts and webpack.serve.ts configuration files?
10. Which libraries are used for UI construction in ETChat, and what is the current status of their migration?
11. How does the QR code authentication and synchronization process work between web and mobile clients in ETChat?
12. What benefits does using TypeScript offer in ETChat’s codebase?
13. What is the function of crunker and how is it utilized in ETChat?
14. How does ETChat ensure code quality and formatting consistency?
15. What files and directories are typically excluded from version control in ETChat's .gitignore?
16. How does the sitemap.xml contribute to ETChat’s search engine optimization (SEO) strategy?
17. What utility does the emoji-picker-react library provide in the application?
18. Describe the purpose and security considerations of using client-side cryptography libraries like crypto-browserify and crypto-js in ETChat.
19. Why is it important to avoid introducing new Bootstrap dependencies in the ETChat project?
20. What recommended learning path is suggested for new developers joining the ETChat project?

---

## Answers

1. ETChat uses XMPP (with OMEMO encryption) for chat synchronization and WebSockets (using Socket.IO) for signaling and real-time synchronization between devices. This dual-protocol approach ensures secure and seamless communication.

2. XMPP enables synchronized communication by delivering messages, updating call logs, and propagating presence status to all of a user's active devices. It ensures that when a user logs into multiple devices, all communication data—including messages and logs—remain consistent and in sync.

3. Converse.js is the main client-side library for managing XMPP communication in ETChat. Its key features include OMEMO end-to-end encryption, multi-user chat support, customizable UI, a plugin architecture, and chat state/roster management.

4. The @comera/comera-protocol-bindings package manages WebRTC signaling for calls. It supports dynamic multi-participant calls, allowing up to 4 active participants simultaneously, with a pool of up to 10 total associated participants.

5. The ETChat development workflow typically involves running npm install to install dependencies, npm run serve to start the development server with live reload (using Webpack), and npm run build for creating production-optimized bundles.

6. ETChat enables PWA features through the use of a manifest.json file, service workers, and proper configuration, which allows users to install the app on their device home screen, run in standalone mode, access offline capabilities, and receive push notifications.

7. Best practices include never storing secrets or sensitive credentials in .env files; instead, sensitive data should be securely fetched from backend APIs, always transmitted in encrypted form, and environment variables should be segregated by environment (development, staging, production).

8. The robots.txt file is not a security measure: (1) it does not prevent direct access to URLs, and (2) malicious bots may ignore its instructions, so private or sensitive areas should always require proper authentication.

9. The webpack.common.ts file contains shared rules for all build environments, such as asset processing and code splitting, while webpack.serve.ts is tailored for development with features like live reload, hot module replacement, and faster rebuilds.

10. ETChat primarily uses Ant Design (antd) for UI components. Bootstrap is still used for some legacy utility classes, but the project is in the process of fully migrating to Ant Design, with a recommendation to avoid adding new Bootstrap dependencies.

11. The web client requests a QR code for authentication by sending a request to the server. The server responds with a base64-encoded PNG QR code. The user scans this QR with the mobile app, resulting in authentication and synchronization of devices for unified messaging.

12. TypeScript provides compile-time error detection, enhances type safety, offers intelligent autocomplete in IDEs, serves as inline code documentation, enforces consistent patterns, and ensures better browser and module compatibility for ETChat.

13. Crunker is used as an audio processing library in ETChat. It can combine, process, and generate final audio files for voice messages, enabling manipulation and creation of audio content for chats.

14. ETChat uses Prettier along with a .prettierignore file to automatically format code and maintain a consistent code style across the project. This is integrated with developer environments and CI/CD pipelines.

15. The .gitignore file excludes node_modules, build artifacts (dist, build), environment files (.env, .env.local), IDE configs (.vscode, .idea), and OS-specific files like .DS_Store and Thumbs.db from version control.

16. The sitemap.xml file defines and organizes pre-login and post-login URLs, informs search engines about site structure and priority, specifies update frequency, and thus improves crawl efficiency and visibility in search results.

17. The emoji-picker-react library provides an emoji selection interface, enabling users to add emojis to messages, react with emojis, and search or categorize them for expressive communication.

18. Crypto-browserify and crypto-js provide cryptographic utilities for client-side encryption, decryption, and hashing within ETChat. They are used for operations like securing user data but must be complemented with secure backend validation and transmission practices due to client-side security limitations.

19. It is important to avoid introducing new Bootstrap dependencies because ETChat is migrating to Ant Design as the primary UI framework. New UI work should use Ant Design for consistency and maintainability.

20. The recommended learning path for new ETChat developers includes studying XMPP and OMEMO basics, reviewing Converse.js and Redux documentation, familiarizing with Ant Design, following project coding standards, and actively participating in code reviews.
