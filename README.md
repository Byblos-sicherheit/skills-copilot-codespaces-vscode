<header>

<!--
  <<< Author notes: Step 1 >>>
  Choose 3-5 steps for your course.
  The first step is always the hardest, so pick something easy!
-->

## Step 1: DHCP Fundamentals — The DORA Process

_Welcome to "Learn DHCP"! :wave:_

**DHCP (Dynamic Host Configuration Protocol)** is a network management protocol used to automatically assign IP addresses and other network configuration parameters to devices on a network. Without DHCP, every device would need to be manually configured with a unique IP address.

### How DHCP Works — The DORA Process

DHCP uses a 4-step process known as **DORA**:

| Step | Message | Direction | Description |
|------|---------|-----------|-------------|
| 1 | **D**iscover | Client → Broadcast | Client broadcasts to find available DHCP servers |
| 2 | **O**ffer | Server → Client | Server offers an IP address from its pool |
| 3 | **R**equest | Client → Broadcast | Client requests the offered IP address |
| 4 | **A**cknowledge | Server → Client | Server confirms the IP lease to the client |

### Key DHCP Concepts

- **Lease**: A temporary assignment of an IP address with an expiry time
- **Scope**: A range of IP addresses a DHCP server can assign
- **Reservation**: A permanent IP assignment tied to a MAC address
- **DHCP Pool**: The collection of IP addresses available for assignment
- **Default Gateway**: Network router address sent to clients
- **DNS Servers**: Name resolution servers sent to clients
- **Lease Time**: How long a client may use an assigned IP before renewal

### :keyboard: Activity: Document the DORA Process

**We recommend opening another browser tab to work through the following activities so you can keep these instructions open for reference.**

1. Navigate to the **Code** tab of your repository.
1. Click **Add file** → **Create new file**.
1. Name the file:
   ```
   dhcp/README.md
   ```
1. Add the following content to document your understanding of DHCP:
   ```markdown
   # DHCP Notes

   ## What is DHCP?
   DHCP (Dynamic Host Configuration Protocol) automatically assigns IP addresses
   and network configuration to devices.

   ## DORA Process
   - **Discover**: Client broadcasts to find a DHCP server
   - **Offer**: Server offers an available IP address
   - **Request**: Client requests the offered address
   - **Acknowledge**: Server confirms the lease

   ## Key Terms
   - Lease: Temporary IP address assignment
   - Scope: Range of addresses the server can assign
   - Reservation: Static IP bound to a MAC address
   ```
1. Select **Commit directly to the `main` branch** and click **Commit new file**.

**Wait about 60 seconds then refresh your repository landing page for the next step.**

</header>

<!--
  <<< Author notes: Step 1 >>>
  Choose 3-5 steps for your course.
  The first step is always the hardest, so pick something easy!
  Link to docs.github.com for further explanations.
  Encourage users to open new tabs for steps!
-->

## Step 1: Leverage Codespaces with VS Code for Copilot

_Welcome to "Develop With AI Powered Code Suggestions Using GitHub Copilot and VS Code"! :wave:_

GitHub Copilot is an AI pair programmer that helps you write code faster and with less work. It draws context from comments and code to suggest individual lines and whole functions instantly. GitHub Copilot is powered by OpenAI Codex, a generative pretrained language model created by OpenAI.

**Copilot works with many code editors including VS Code, Visual Studio, JetBrains IDE, and Neovim.**

Additionally, GitHub Copilot is trained on all languages that appear in public repositories. For each language, the quality of suggestions you receive may depend on the volume and diversity of training data for that language.

Using Copilot inside a Codespace shows just how easy it is to get up and running with GitHub's suite of [Collaborative Coding](https://github.com/features#features-collaboration) tools.

> **Note**
> This skills exercise will focus on leveraging GitHub Codespace. It is recommended that you complete the GitHub skill, [Codespaces](https://github.com/skills/code-with-codespaces), before moving forward with this exercise.

### :keyboard: Activity: Enable Copilot inside a Codespace

**We recommend opening another browser tab to work through the following activities so you can keep these instructions open for reference.**

Before you open up a codespace on a repository, you can create a development container and define specific extensions or configurations that will be used or installed in your codespace. Let's create this development container and add copilot to the list of extensions.

1. Navigating back to your **Code** tab of your repository, click the **Add file** drop-down button, and then click `Create new file`.
1. Type or paste the following in the empty text field prompt to name your file.
   ```
   .devcontainer/devcontainer.json
   ```
1. In the body of the new **.devcontainer/devcontainer.json** file, add the following content:
   ```
   {
       // Name this configuration
       "name": "Codespace for Skills!",
       "customizations": {
           "vscode": {
               "extensions": [
                   "GitHub.copilot"
               ]
           }
       }
   }
   ```
1. Select the option to **Commit directly to the `main` branch**, and then click the **Commit new file** button.
1. Navigate back to the home page of your repository by clicking the **Code** tab located at the top left of the screen.
1. Click the **Code** button located in the middle of the page.
1. Click the **Codespaces** tab on the box that pops up.
1. Click the **Create codespace on main** button.

   **Wait about 2 minutes for the codespace to spin itself up.**

1. Verify your codespace is running. The browser should contain a VS Code web-based editor and a terminal should be present such as the below:
   ![Screen Shot 2023-03-09 at 9 09 07 AM](https://user-images.githubusercontent.com/26442605/224102962-d0222578-3f10-4566-856d-8d59f28fcf2e.png)
1. The `copilot` extension should show up in the VS Code extension list. Click the extensions sidebar tab. You should see the following:
   ![Screen Shot 2023-03-09 at 9 04 13 AM](https://user-images.githubusercontent.com/26442605/224102514-7d6d2f51-f435-401d-a529-7bae3ae3e511.png)

**Wait about 60 seconds then refresh your repository landing page for the next step.**
<!--
  <<< Author notes: Step 1 >>>
-->

## Step 1: DHCP Fundamentals — The DORA Process

_Welcome to "Learn DHCP"! :wave:_

**DHCP (Dynamic Host Configuration Protocol)** is a network management protocol used to automatically assign IP addresses and other network configuration parameters to devices on a network.

### How DHCP Works — The DORA Process

| Step | Message | Direction | Description |
|------|---------|-----------|-------------|
| 1 | **D**iscover | Client → Broadcast | Client broadcasts to find available DHCP servers |
| 2 | **O**ffer | Server → Client | Server offers an IP address from its pool |
| 3 | **R**equest | Client → Broadcast | Client requests the offered IP address |
| 4 | **A**cknowledge | Server → Client | Server confirms the IP lease to the client |

### Key DHCP Concepts

- **Lease**: A temporary assignment of an IP address with an expiry time
- **Scope**: A range of IP addresses a DHCP server can assign
- **Reservation**: A permanent IP assignment tied to a MAC address
- **DHCP Pool**: The collection of IP addresses available for assignment

### :keyboard: Activity: Document the DORA Process

1. Navigate to the **Code** tab of your repository.
1. Click **Add file** → **Create new file**.
1. Name the file: `dhcp/README.md`
1. Add content documenting the DORA process and key DHCP terms.
1. Make sure your file includes the word `Discover` and `Acknowledge`.
1. Commit directly to `main`.

**Wait about 60 seconds then refresh your repository landing page for the next step.**

<footer>

---

Get help: [Post in our discussion board](https://github.com/orgs/skills/discussions) &bull; [Review the GitHub status page](https://www.githubstatus.com/)

&copy; 2024 Byblos Sicherheit &bull; [MIT License](https://gh.io/mit)

</footer>
