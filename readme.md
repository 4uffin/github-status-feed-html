# **GitHub Status Feed Client**

This is a single-file, responsive web application built with **HTML, CSS, and vanilla JavaScript** that allows you to view the current status messages of various GitHub users in a clean, scrollable feed.

It's designed to be a lightweight tool for quickly checking the presence status (message and emoji) of users you follow or search for, filtering out users who don't have an active status set. It leverages the **GitHub GraphQL API** for efficient data retrieval.

## **✨ Features**

* **Real-time Status Feed:** Displays the current public status (emoji and message) for a list of GitHub users.  

* **Two Query Modes:**  

  1. **Search:** Fetch the latest active statuses from the top N users on GitHub.
   
  2. **List:** Fetch statuses for a specific, comma-separated list of usernames.  

* **Personal Access Token (PAT) Support:** Optionally paste a GitHub Personal Access Token to increase the API rate limit, allowing for more frequent or larger data fetches.  

* **Token Persistence:** Option to securely save the PAT locally in your browser's **LocalStorage** for future sessions.  

* **Jump Functionality:** Quickly fetch and highlight the status of a specific user.  

* **Responsive Design:** Optimized for viewing on both desktop and mobile devices.  

* **Emoji Control:** Select between **Twemoji** (consistent, cross-platform images) or **GitHub's** default emoji image style.  

* **Client-Side Configuration:** Easily adjust the fetch count, query type, and display settings (like font size and sort order) via the settings panel.

## **🚀 How to Use**

Since this is a single HTML file, you can run it directly in any modern web browser.

### **Prerequisites**

* A modern web browser (Chrome, Firefox, Edge, Safari, etc.).  
* An active internet connection to reach the GitHub GraphQL API.  
* A GitHub Personal Access Token (PAT) for higher rate limits.

### **Running the Client**

1. **Download:** Save the index.html file to your computer.  
2. **Open:** Double-click the file to open it in your browser.

### **Settings and Configuration**

The application is highly configurable via the **Settings Panel** on the right (or at the top on mobile).

| Setting | Description | Default |
| :---- | :---- | :---- |
| **GitHub Token** | Paste a Personal Access Token (PAT) here to get higher API rate limits. See the section below for how to generate one. | None |
| **Remember token** | Check this to save the token securely in your browser's LocalStorage. | Off |
| **Users to fetch** | The number of users to fetch when using the **Search** query type (max 500). | 50 |
| **Query type** | Toggle between **Search** (fetch top N users) and **Fetch by username list** (use the list below). | Search |
| **Comma-separated usernames** | Enter a list of specific GitHub logins (e.g., octocat, torvalds) when using the **Fetch by username list** mode. | Empty |
| **Emoji style** | Choose how emojis are rendered (Twemoji vs. GitHub style). | Twemoji |
| **Font size** | Adjust the display font size for the entire application. | 13 |

Once settings are adjusted, click **Apply** to save them and run a new fetch.

## **🔑 Generating a GitHub Personal Access Token (PAT)**

Using a PAT is the best way to avoid GitHub's strict API rate limits. You only need to grant it the minimal scope required to read public data.

**Crucial Note:** Treat your PAT like a password. It should never be shared publicly or committed to source code.

### **1. Navigate to Settings**

1. Log in to your GitHub account.  
2. Click on your **profile photo** in the upper-right corner.  
3. Click **Settings**.  
4. In the left sidebar, scroll down to the bottom and click **Developer settings**.  
5. In the next left sidebar, click **Personal access tokens**.  
6. Click **Tokens (classic)**.

### **2. Generate and Configure the Token**

1. Click the **Generate new token (classic)** button.  
2. Set the **Note** to something descriptive (e.g., Status Feed Client).  
3. Set an **Expiration** date (for security, or select No expiration for simplicity).  
4. Under **Select scopes**, **ONLY** check the **read:user** checkbox. This is the only permission needed for this client. **Do not check repo or other powerful scopes.**

### **3. Create and Copy**

1. Click the **Generate token** button at the bottom of the page.  
2. **IMMEDIATELY COPY THE GENERATED TOKEN.** You will not be able to see it again once you leave the page.

You can now paste this token into the "GitHub Token" field in the client's Settings Panel.

## **📜 License**

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE).
