# Project 100 Code Repository Onboarding

Welcome to the Project 100 code repository! This document will guide you through setting up your development environment, understanding the project structure, and using Git for version control. If you have any questions, please reach out to [@DistractedGames](https://discordapp.com/users/358030688785793026).

### First thing's first...

## Writing Clean, Consistent, and Typed Code
Before diving into setting up your development environment, it's crucial to establish a standard for how we write code. All team members must follow the [Roblox Lua Style Guide](https://roblox.github.io/lua-style-guide/) and use type annotations from the start. These are not optional best practices—they are required for maintaining clean, readable, and efficient code across our team.

### Why This Matters
1. **Consistency Across Developers** – Everyone writing code the same way makes it easier to read, debug, and collaborate. When code is predictable, it reduces the time spent deciphering different formatting styles.

2. **Better Code from the Start** – Applying the style guide and type annotations as you write ensures that your code is structured correctly from the beginning. Writing sloppy code and trying to "fix" it later only creates more work for you and the team.

3. **Faster Code Reviews and Merge Requests** – Clean, well-typed code makes it much easier for me (and others) to review, suggest improvements, and merge changes quickly. Poorly formatted or loosely typed code slows down the process and increases the risk of bugs.

4. **Improved Debugging and Autocompletion** – Type annotations help identify issues early, provide better error messages, and enhance autocompletion in your IDE. This actually makes writing code easier and faster in the long run.

### Expectations for Code Quality
- **Write properly formatted code from the start** – Do not write messy or untyped code and then try to clean it up later. It should be correct as you write it.
- **Use meaningful variable and function names** – Avoid vague names like `data`, `x`, or `stuff`. Your code should be self-explanatory.
- **Comment where necessary** – Explain complex logic, but don’t over-comment obvious things. Comments should clarify why something is done, not what the code does (unless it's non-obvious).
- **Use type annotations everywhere** – This is mandatory for functions, tables, and any variables where types matter.

By following these guidelines, we ensure that our team operates smoothly, efficiently, and with high-quality code. The better we adhere to these practices, the more time we save and the better the project will be.

Now, let’s get you set up! 🚀

---

### Table of Contents
- [Getting Started](#getting-started)
   - [Setting up Visual Studio Code](#setting-up-visual-studio-code)
   - [Installing Git](#installing-git)
   - [Cloning the Repository](#cloning-the-repository)
- [Understanding the Repository](#understanding-the-repository)
   - [Project Structure](#project-structure)
   - [Key Directories](#key-directories)
- [Git Workflow and Branching Strategy](#git-workflow-and-branching-strategy)
   - [Keeping Your Code Updated](#keeping-your-code-updated)
   - [Working with Branches](#working-with-branches)
   - [Making Changes and Commiting](#making-changes-and-committing)
   - [Writing Commit Messages](#writing-commit-messages-in-visual-studio-code)
   - [Keeping Your Branch Updated](#keeping-your-branch-updated)
   - [Merging and Deleting Your Branches](#merging-and-deleting-your-branches)

---

## Getting Started
### Setting up Visual Studio Code
For this project, we will use **Visual Studio Code (VS Code)** as our development environment. If you're completely new to using an external IDE, such as Visual Studio Code and/or have never used SCM (Source Control Management, sometimes referred to as Version Control) this guide will walk you through setup and basic usage using the Visual Studio Code's user interface (*and keyboard shortcuts*). If you start feeling more
comfortable, feel free to use the command line interface (CLI). It's just better in a lot of ways, but takes some practice.

*Note: If you prefer too use another IDE, such as Neovim, then you likely are already well versed in this process. Sadly coding with Luau in Vim or Neovim isn't as well supported as VS Code (shocker, I know), so note that you will be at a disadvantage trying to code using that.*

Follow these steps to set up your workspace:

1. Download and Install VS Code from [Visual Studio Code](https://code.visualstudio.com/).
2. Sign into VS Code using your GitHub account
   - Click on the **Accounts** icon ![accountsicon](./Images/AccountsIcon.png) in the lower-left corner of VS Code.
   - Select Sign in with GitHub and follow the prompts.
   - Signing in allows you to sync your settings across devices and ensures you already have access to our repository.
   - **Note**: VS Code can also be accessed from a web browser at [vscode.dev](https://vscode.dev/), but it has limitations in extension support. It is useful for quick edits on the go but is not a full replacement for the desktop version.
3. Install required extensions:
   - Open the **Extensions Tab** by clicking the **Extensions** icon ![extensionsicon](./Images/ExtensionsIcon.png) on the sidebar or by pressing `Ctrl + Shift + X`.
   - Extensions in VS Code allow you to enhance functionality, such as adding support for specific languages and tools. This flexibility makes VS Code highly customizable for different development needs. You may find a few other extensions that help yourpersoanl workflow or maybe just a new theme for Visual Studio Code.
   - Search for and install the following extensions:
      - [Rojo](https://marketplace.visualstudio.com/items?itemName=evaera.vscode-rojo)
      - [Roblox LSP](https://marketplace.visualstudio.com/items?itemName=JohnnyMorganz.RobloxLsp)
      - [Selene](https://marketplace.visualstudio.com/items?itemName=JohnnyMorganz.selene)
      - [StyLua](https://marketplace.visualstudio.com/items?itemName=JohnnyMorganz.stylua)
4. Optional Recommended Extension:
   - [Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme) – Enhances file and folder icons in the Explorer for better visual organization.
5. Enable Auto Save:
   - Go to **File** > **Auto Save** and enable it.
   - This feature saves files automatically upon changes, preventing common issues caused by forgetting to manually save with `Ctrl + S`.

**Note: You do not need to manually set up a Rojo project—our repository comes pre-configured for you.**

#### 🌟The Command Palette🌟
Directly from the VS Code documents themselves, they state that, "The most important key combination to know is `Ctrl+Shift+P`, which brings up the **Command Palette**. From here, you have access to all functionality within VS Code, including keyboard shortcuts for the most common operations."

Sure enough, this is a super easy way to operate in VS Code and I use it all of the time myself. If you want to learn to start moving through VS Code at lightning speed, stop using the UI and use the **Command Palette** instead. I'll be sure to include commands for this as relevant.

For a deeper dive into the **Command Palette** (and Visual Studio Code as a whole) visit the [Visual Studio Code Documentation](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).

---

### Installing Git
Git is required for managing code changes and collaboration. It allows you to maintain a local copy of the repository on your system, edit your own version of the Project 100 code before commiting changes, and stay up to date with modifications made by other contributors. We will explore these processes in more detail later in this document.

1. **Download Git** from [git-scm.com](https://git-scm.com/downloads)
2. Follow the installation instructions for your OS.
3. Verify installation:
   - In VS Code, open a new Terminal window (`` Ctrl + ` `` or, at the top of the screen, got to **Terminal** > **New Terminal**).
   - The Terminal window should open at the bottom of the sreen.
   - Inside the Terminal Window, type the following command and press `Enter`:
      ```bash
      git --version
      ```
      If you see the installed version, you're good. If you have issues, reach out to [@DistractedGames](https://discordapp.com/users/358030688785793026).

---

### Cloning the Repository
Once Git is installed, you need to clone the project 100 repository to your local machine. This will create a folder named `Project100` automatically, so you do not need to create it manually. If you want to store the project in a specific location, such as the `D:` drive, on your `Desktop`, or in your `Documents` folder, you can navigate there first before cloning. If you're familiar with using the command line interface, you should do so in the Terminal Window now. Otherwise, you can go to **File** > **Open Folder** (or press `Ctrl + k` then `Ctrl + o`) and select the parent directory you want to store the `Project100` folder in.

#### Steps to Clone the Repository
1. Find the Repository Link on GitHub:
   - Navigate to the Project 100 repository on GitHub located [here](https://github.com/Project-100-Official/Project100).
   - Click the `<> Code` button at the top of the repository page:

      <img src="https://docs.github.com/assets/cb-13128/mw-1440/images/help/repository/code-button.webp" alt="clone" width="400"/>

   - Copy the provided HTTPS link:

      <img src="https://docs.github.com/assets/cb-60499/mw-1440/images/help/repository/https-url-clone-cli.webp" alt="clone" width="400"/>

2. Open a Teminal and Clone the Repository:
   - Ensure the terminal is showing your desired folder location. For example, the `D:` would look like this:

   ```bash
      $ D:\>
   ```

   - Clone the repository by typing the following and pressing `Enter`:

   ```bash
      git clone https://github.com/Project-100-Official/Project100.git
   ```

3. Open the Project in VS Code:
   - Open a folder as covered in [Cloning the Repository](#cloning-the-repository) and select the newly created `Project100` folder.
   - Open the **Explorer Tab** by clicking on the **Explorer** icon ![explorericon](./Images/ExplorerIcon.png) or by pressing `Ctrl + Shift + E`. 

You should now see the project files in the **Explorer Tab**, ready for development.

---

## Understanding the Repository
Understanding the folder structure will help you navigate and contribute efficiently.

### Project Structure

```plaintext
Project100/
├── .vscode/                     # VS Code workspace settings
├── Onboarding                   # Contains this walkthrough and dependencies
├── src/                         # Main source code
│   ├── ReplicatedFirst/         # Reserved for select scripts, such as loading screens
│   ├── ReplicatedStorage/       # Scripts that must be accessible to both server and clients
│   ├── ServerScriptService/     # Scripts that must not be accessible to clients
│   ├── ServerStorage/           # Mostly reservered for project readme files (check it out)
│   ├── StarterCharacterScripts/ # Scripts that must go on the character directly (reset on respawn)
│   ├── StarterPlayerScripts/    # The majority of client-side scripts, including most GUI scripts
├── .gitignore                   # List of folders or files to ignore synching to the repo
├── aftman.toml                  # Manages Rojo
├── default.poject.json          # Allows structure of project to work
├── README.md                    # Project overview and setup guide
├── selene.toml                  # Settings file for aditional Roblox linter
```

### Key Directories

- #### Source Folders
   Each of the directories in `src` correspond to what you would see in Roblox Studio. Inside each of these Roblox directories is a `Source` folder. All scripts will exist inside of these folders and **only** inside these folders. If you think you have a reason to place a script elsewhere, such as `StarterGui`, I would advise against it. Simply make your UI scripts inside of `StarterPlayerScript/Source`. This not only keeps all of the code in easy to find locations, but also will allow for easier updates through packages. Making 100 floors using 100 places means we need to consider maintainability of the codebase and this will go a long way toward achieving with that.

- #### `ServerStorage`
   `ServerStorage` is a special directory. At this time, no code-running scripts are going to go inside of it. I have however decided to place useful Readme files inside its `Source` folder. These Readme files will be designed to allow other devs to understand how specific features work. I call out the different files the feature relies on, give example usages, and explain how the code works in a relatively general sense so if someone needs to utilize one of those features, they can quickly and easily understand things without having to open multiple scripts and follow breadcrumbs of information. If you write up a new feature, I highly recommend you create a Readme for it as well, though I will make all attempts to do so if you decide not to.

- #### `ReadMe` Files, `Utility`, and `SharedConstants`
   Make sure to check the Readme files for useful methods and modules that will be added to the repo. A number of the added utilities will save you time and effort and some will be mandatory to use. For example, in `ReplicatedStorage/Source/SharedConstants`, we will have many of the game's configurations, themes, and Enums. Enums are best used for both avoiding typos and for getting an auto-complete list of available options for a specific use. As an example, if you are working with weapons in any way, you should be requiring the `WeaponType` module. This will then give you an up-to-date list of all the weapon types in the game without having to guess or look it up.

---

## Git Workflow and Branching Strategy
In this project, we follow a structured Git branching strategy to ensure smooth collaboration and code management. If you’re new to Git, don’t worry—this section will guide you through the process of working with branches, committing changes, and keeping your code up to date.

For more specific details about the branching strategy, please review the [Git Branching Strategy](./GitBranchingStrategy.md) guide. 

#### Main Branches
- **master** – Main branch containing the latest development changes.
- **stable** – Reflects the latest production-ready release.

#### Supporting Branches
These branches have a limited lifespan and serve specific purposes:
- **feature-*** – New features or enhancements.
- **bug-*** – Fixes for known issues.
- **hotfix-*** – Critical fixes for the production environment.
- **refactor-*** – Code optimization and restructuring.

---

### Keeping Your Code Updated
Before creating a new branch, you must always pull the latest changes from `origin/master` (`origin` meaning from the online GitHub repo). This ensures your branch is up to date and prevents conflicts.

🚨 You should never work directly in `master` adn definitely not `stable`! Always create a new branch from `origin/master`.

#### Fetching the Latest Changes ( prior to creating a new branch )
Using CLI:
```bash
git fetch origin                       # Fetch latest changes
git checkout master                    # Ensure you're on master (but not working in it)
git reset --hard origin/master         # Reset master to match origin/master
```

Using VS Code UI:
1. Open the **Source Control** panel by clicking the **Source Control** icon ![sourcecontrolicon](./Images/SourceControlIcon.png) or by pressing `Ctrl + Shift + G`.
2. Click on the "..." button (More Actions):

   ![moreactions](./Images/MoreActions.png)

3. Hover over **Pull, Push** and select **Pull (Rebase)**

Using the Command Palette:
1. Open the **Command Palette** with `Ctrl + Shift + P`
2. Type 'pull rebase' and it should be the top option selected, so you can just hit `Enter`
   - Note that the Command Palette is a fuzzy search, so as you type it updates the results. You may only need to type 'pullr' to get the correct option. Also note that it saves your most recent actions, so you may not have to type anything at all if you've used the command recently.

🚨 This ensures your local `master` branch exactly matches `origin/master` before branching.

---

### Working with Branches

#### Creating a New Branch
As per the [Git Branching Strategy](./GitBranchingStrategy.md), when adding a new feature or bug fix, you **must** create a branch from `origin/master`. Hotfixes must actually branch from `stable`.

When making a new feature branch, the name of the branch should be `feature-` followe dby the name of the feature. For example, a double-jump feature branch would be named `feature-DoubleJump`. If making a bug fix branch, the name should be `bug-` followed by a name for the bug (try to remain short and concise here). Finally, for hotfix branches, `hotfix-` and the hotfix name. (Unfamiliar with what a hotfix is? Check [here](https://en.wikipedia.org/wiki/Hotfix))

Using CLI:
```bash
git fetch origin                                    # Ensure you have the latest changes
git checkout -b feature-FEATURE_NAME origin/master  # Create a new branch from origin/master
git push -u origin feature-FEATURE_NAME             # Push branch to GitHub
```

Using VS Code UI:
1. Open the **Source Control** panel (`Ctrl + Shift + G`) and click on the **branch name** (or on the **branch name** at the bottom left corner of the workspace window):

   ![branchname](./Images/BranchName.png)

2. Select "**Create new branch from...**" and select `origin/master`
   - Your local `master` shgould be up to date if you've followed the workflow, so you could also branch from `master` here instead.

3. Name the new branch according to the naming rules mentioned at the start of this section (e.g. `feature-*`, `bug-*`, etc.)

Using the Command Palette:
- Open the Command Pallet and type 'create branch from' and follow the same steps as the UI above.

This will place you in your own copy of the `master` code repo and allow you to develop without interfering with any other code changes and without being interferred with.

---

### Making Changes and Committing
After editing, creating, or deleting files, you need to **stage**, **commit**, and **push** your work.

Using CLI:
```bash
git add .                                 # Stage all changes
git commit -m "Add feature description"   # Commit changes with a message
git push origin feature-*                 # Push changes to GitHub
```
Replace `*` with the actual name of your feature branch.

*Note: You can stage specific files for changes rather than all changes by using `git add [InsertFileLocation].FileName`*

Using VS Code:
1. Open **Source Control** (`Ctrl + Shift + G`)
2. Click the `+` button next to modified files (or click the "**Stage All**" `+`, arrow pointing to it):
   
   ![stagechnages](./Images/StageChanges.png)

3. Enter a commit message (see [below](#writing-commit-messages-in-visual-studio-code)).
4. Click "**Commit**"

If, at this point, your branch has not been published to the online repository, the "**Commit**" button will change to say "**Publish Branch**". Go ahead and click this to publish your new branch to the online repo. Otherwise, the button should show "**Sync Changes**". Clicking this will again push the changes to the online repo.

You may encounter the button showing somethign similar to the following:

![synchchanges](./Images/SyncChanges.png)

In this case, the number shown adn the down arrow means there are 65 changes in the origin that need to be synced to you loacal repository. Make sure to stay updated.

---

### Writing Commit Messages in Visual Studio Code
Commit messages are an essential part of version control. They serve as a record of changes made to the codebase and help you (and others) understand the purpose of each change. A good commit message is short, clear, and descriptive. Here are a few tips:
- **Start with a brief summary**: Describe the change in one concise line. For example: `Fix typo in README file` or `Add new character pathfinding functionality`.
- **Use the imperative mood**: Write messages as if you are giving commands, e.g., "*Add...*" instead of "*Added...*".
- **Focus on the *why* or *what*, not the *how***: Explain the purpose or result of the change instead of the technical details. Save the technical information for the detailed message (if needed).
- **Avoid vague terms**: Be specific and avoid phrases like "small fixes" or "updated stuff."

#### Accidentally Pressed Commit Before Adding a Message?
No worries! If you accidentally commit without leaving a message, VS Code allows you to fix this easily. It should open the commit in the workspace window. Simply type your commit message at the top and close the file (`Ctrl + w`) to save it. You can also amend the last commit and add a message:
1. Open the **Source Control** view (`Ctrl + Shift + G`).
2. Make sure no new changes are staged.
3. Click on the menu next to "Commit" and select "**Commit (Ammend)**."
4. You'll be able to provide a commit message or change the commit message from the window described above once it opens in the workspace.

#### Adding Detailed Messages
Sometimes, a simple one-liner isn’t enough to fully explain your changes. You can add a detailed message alongside your summary:
1. Write the concise summary in the commit message box.
2. Using `Shift + Enter`, leave an empty line below the summary.
3. Add a more detailed explanation of your changes. For example:
```plaintext
Add player health regeneration feature

added logic for regenerating player health every 5 seconds. Also fixed a bug where health regeneration stopped under certain conditions.
```

#### Using GitHub Copilot to Generate Messages
VS Code also has a "**Generate Commit Message with Copilot**" option:

![generatewithcopilot](./Images/GenerateCopilot.png)

Copilot can analyze your changes and suggest a commit message for you. However, it's important to review the message before committing. Sometimes the suggested messages might not fully capture the intent or context of your changes, so make sure to edit or refine them as needed.

---

### Keeping Your Branch Updated
While working on a branch, you should regularly pull from `origin/master` using **Pull (Rebase)** to stay updated.

Using CLI:
```bash
git fetch origin              # Get latest changes
git rebase origin/master      # Reapply your changes on top of the latest master
```

Using VS Code UI:
1. Open the **Source Control** view (`Ctrl + Shift + G`).
2. Click on the "..." button (More Actions):

    ![moreactions](./Images/MoreActions.png)

3. Hover over **Pull, Push** and select **Pull (Rebase)**

🚨 Rebasing prevents merge conflicts and keeps your feature branch in sync with master.

---

### Merging and Deleting Your Branches
🚨 **IMPORTANT**: You will only ever be deleting your **own** branches. **Never** delete another developer's branch unless explicietly asked to.

Once you’ve completed work on your feature branch (or bug fix/hotfix), the next step is to create a **Pull Request** on GitHub to mergeyout feature branch into the `master` branch. Then you can cleanup your local branches.

Follow these steps to make sure everything is smooth and well-organized:

#### Step 1: Sync your local branch to the GitHub repository
Using CLI:
1. **Ensure you're in your feature/bug/hotfix branch (using a feature branch as demonstration):**
   - Open the terminal and run:
      ```bash
      git checkout feature-*
      ```
      Replace `*` with the actual name of your feature branch.
   - This will set you in your local version of the `feature-*` branch.
2. **Push the feature branch up to GitHub:**
   - Run:
      ```bash
      git push origin feature-*                 # Push changes to GitHub
      ```
      Replace `*` with the actual name of your feature branch.

Using VS Code UI:
1. **Switch to the `feature-*` branch:**
   - Open the **Source Control** panel (`Ctrl + Shift + G`) and click on the **branch name** (or on the **branch name** at the bottom left corner of the workspace window):

      ![branchname](./Images/BranchName.png)

   - Select `feature-*` (not `origin/feature-*`)
   Replace `*` with the actual name of your feature branch.

2. In the **Source Control** view, click on the "..." button (More Actions):

    ![moreactions](./Images/MoreActions.png)

3. Hover over **Pull, Push** and select **Push**
   - Make sure there are not unstaged or committed changes.

#### Step 2: Create a Pull Request
The next step is to create a pull request to merge your feature branch into `master` on GitHub:

1. Navigate to the [GitHub repository](https://github.com/Project-100-Official/Project100/)
2. Open the **Pull Requests** tab and select **New Pull Request**, or you may see the following, in which case, if it's your feature branch, click the **Compare & pull request** button:

   ![pullrequest1](./Images/PullRequest1.png)

3. Ensure you've selected your feature branch as the **source** and `master` as the **target**:

   ![pullrequest2](./Images/PullRequest2.png)

4. Add a clear title and description for the pull request to explain the changes you’ve made.

**Note**: Only the project lead (@DistractedGames) will review and handle the merging of pull requests. Developers are responsible for creating the pull request but should **not merge it themselves**.

#### Step 3: Delete the Local Feature Branch
After creating the pull request, you can delete the local feature branch to keep your workspace tidy:

Using CLI:
- Run the command:
  ```bash
  git branch -d feature-*
  ```
*Note: You may need to use a capital `-D` if it has an issue deleting it.

Using VS Code UI:
1. Open the **Source Control** view (`Ctrl + Shift + G`).
2. Click on the "..." button (More Actions):

    ![moreactions](./Images/MoreActions.png)

3. Hover over **Branch** and select **Delete Branch...**
4. Select your feature branch

#### Step 4: Published Feature Branch Cleanup
Once the pull request has been reviewed and merged by @DistractedGames, the published feature branch on GitHub will be cleaned up as needed. You don’t need to worry about deleting it yourself—@DistractedGames will handle this step to ensure proper repository management.
