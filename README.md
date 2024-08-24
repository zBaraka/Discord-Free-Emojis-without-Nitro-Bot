# Discord Emoji Bot

This bot responds to commands by sending specific emojis.
## This works without Discord Nitro
This bot is for non-Nitro users.
Note that it might not work in some servers, but it will work in DMs, GDMs, and most servers.

![example](https://github.com/user-attachments/assets/2b601492-31dc-42c2-aed3-caa8113d02b4)

Follow the instructions below to install, configure, and run the bot.

## Installation

### Step 1: Set Up Your Bot

1. **Enable User Installation**
   - Navigate to your bot's settings on the Discord Developer Portal.
   - Go to your bot > `Installation`.
   - Enable "Allow users to install your bot."
   - Here’s the link to your bot’s installation settings:
     ```
     https://discord.com/developers/applications/[bot-id]/installation
     ```

2. **Add the Bot to Your Profile**
   - Go to your bot's profile page on Discord.
   - Click on the "Add to Profile" button, which may be labeled as "Try Now."
   - This step will link your bot to your Discord account.

3. **Download the Bot Code**
   - Clone or download the bot's code to your local machine.

### Step 2: Install Necessary Packages

1. **Install Node.js**
   - Ensure that you have [Node.js](https://nodejs.org/) installed on your system. You can check by running:
     ```bash
     node -v
     ```
   - If Node.js is not installed, download and install it from the official website.

2. **Install Required Packages**
   - Navigate to the directory where you downloaded the bot's code.
   - Run the following command to install the necessary npm packages:
     ```bash
     npm install discord.js @discordjs/rest discord-api-types
     ```

## Configuration

### Step 1: Add Emojis to Your Bot's Dashboard

1. **Access the Emoji Dashboard**
   - Navigate to your bot's emoji settings in the Discord Developer Portal:
     ```
     https://discord.com/developers/applications/[bot-id]/emojis
     ```

2. **Upload Emojis**
   - Upload the desired emojis that your bot will use.

3. **Copy Emoji Markdown**
   - Once an emoji is uploaded, click the "Copy Markdown" button (found next to the delete button for each emoji).
   - This copies the markdown for the emoji, which looks something like `<:emojiName:emojiID>`.

### Step 2: Update the Bot Code with Emojis

1. **Locate the Emoji Commands Section**
   - In the bot code, find the `emojiCommands` object. This is where you will define which emojis correspond to which commands.

2. **Add Your Emojis**
   - For each command, replace the placeholder `<exampleX>` with the markdown you copied for the corresponding emoji.
   - Ensure that the command names in the `emojiCommands` object match the command names in the `commands` array below.

   Example:
   ```javascript
   const emojiCommands = {
       'smiley': '<:smiley:123456789>',
       'wink': '<:wink:987654321>',
       // Add more commands as needed
   };
   ```

3. **Update Command Names and Descriptions**
   - Ensure that each command in the `commands` array has a matching entry in the `emojiCommands` object. The command name must be lowercase and should not contain any spaces.

   Example:
   ```javascript
   const commands = [
       {
           name: 'smiley',
           description: 'Responds with the "Smiley Emoji"',
       },
       {
           name: 'wink',
           description: 'Responds with the "Wink Emoji"',
       },
       // Add more commands as needed
   ];
   ```

### Step 3: Enable Server Members Intent

1. **Activate the Required Intent**
   - In the Discord Developer Portal, navigate to your bot's settings.
   - Under the "Bot" tab, scroll down to "Privileged Gateway Intents."
   - Activate the "Server Members Intent." 

## Running the Bot

After you've configured the emojis:

1. Save the changes in your bot's code.
2. Run the bot using Node.js:
   ```bash
   node emoji.js
   ```
3. Your bot should now respond to the specified commands with the corresponding emojis.

## Notes

- Ensure your bot is running continuously. It will only work while this code is running. You can also use a hosting service.
- If you add or change emojis later, update the code accordingly and re-run the bot to apply the changes.
