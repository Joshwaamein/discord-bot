# Discord-Bot

The Discord MusicBot, configured in late 2024, is designed to play music from YouTube in your Discord server. This documentation provides an overview of its setup, configuration, and usage.

## Deployment and Configuration

The bot is deployed as a clone of the [Just-Some-Bots/MusicBot](https://github.com/Just-Some-Bots/MusicBot) repository

To edit the bot's configuration:
1. Navigate to the configuration directory:bash
    `cd /home/discord-bot/MusicBot/config`
2. Edit the `options.ini` file:bash
    `nano options.ini`

## Automatic Startup

The bot is configured to start automatically after system boot using a cron job running as root:

1. To edit the cron job, switch to the root user and run:
    `sudo su crontab -e`
2. You will see the following entry:text
    `@reboot sleep 15 && /home/discord-bot/MusicBot/run.sh >> /home/discord-bot/MusicBot/operating-log.txt`

## Key Commands

Here are some essential commands for controlling the MusicBot:

- `!play <URL/query>`: Play audio from a URL or search YouTube
- `!queue`: Display the current queue
- `!skip`: Vote to skip the current track
- `!volume [number]`: Adjust or display the volume
- `!pause` / `!resume`: Pause or resume playback
- `!summon`: Connect the bot to your voice channel
- `!disconnect`: Disconnect the bot from voice

For a full list of commands, refer to the [official documentation](https://just-some-bots.github.io/MusicBot/using/commands/)
## System Maintenance

The device running the bot is patched by the local Ansible server's update playbook. Ensure that this playbook is kept up-to-date for optimal security and performance.

## Security Note

**Important:** Never share your bot token. If compromised, immediately regenerate it in the Discord Developer Portal (https://discordpy.readthedocs.io/en/stable/discord.html).

## Spotify Integration

### Generating the Spotify API key

https://stevesie.com/docs/pages/spotify-client-id-secret-developer-api

### Accessing the Spotify API key

https://developer.spotify.com/dashboard/94669b3d77084cd4822dbedabb157d8b/settings

## Troubleshooting

If you encounter issues:

1. Check the operating log:
    `cat /home/discord-bot/MusicBot/operating-log.txt`
2. Verify the bot's status in Discord Developer Portal
3. Ensure the configuration file (`options.ini`) is correctly set up

For more detailed configuration options, consult the [official configuration guide](https://just-some-bots.github.io/MusicBot/using/configuration/).
