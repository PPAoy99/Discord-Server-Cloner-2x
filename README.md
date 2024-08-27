const { Client, GatewayIntentBits } = require('discord.js');
const { joinVoiceChannel } = require('@discordjs/voice');
const client = new Client({
    intents: [
        GatewayIntentBits.Guilds
    ]
});

client.once('ready', async () => {
    console.log('Logged in as ' + client.user.tag);
    setInterval(async () => {
        const channelId = 1277804045469483068';
        const guildId = '1277112441054167093เน';
        try {
            const channel = await client.channels.fetch(channelId);
            joinVoiceChannel({
                channelId: channel.id,
                guildId: guildId,
                adapterCreator: channel.guild.voiceAdapterCreator,
            });
        } catch (error) {
            console.error(error);
        }
    }, 1000);
});

client.login('MTI3NzYyNDUzNTU4MzE2NjUxNQ.GRSKCj.WvhzdMwLCe2kc0ryj96fcooItAznJ0sWVTBbDw');
