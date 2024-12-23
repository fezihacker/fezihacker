module.exports = (req, res) => {
  const channels = [
    { name: 'Kanal 1', url: 'http://eu8rep.top/get.php?username=crqqx315&password=mdgkset&type=m3u_plus&output=mpegts)' },
    { name: 'Kanal 2', url: 'http://url-e-kanalit-2.com' },
    { name: 'Kanal 3', url: 'http://url-e-kanalit-3.com' },
  ];

  let m3uContent = '#EXTM3U\n';
  channels.forEach(channel => {
    m3uContent += `#EXTINF:-1, ${channel.name}\n`;
    m3uContent += `${channel.url}\n`;
  });

  res.setHeader('Content-Type', 'audio/x-mpegurl');
  res.setHeader('Content-Disposition', 'inline; filename="playlist.m3u"');
  res.send(m3uContent);
};
