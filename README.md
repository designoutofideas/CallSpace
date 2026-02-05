# 📡 Call Space

**Speak Freely Across the Universe**

Peer-to-peer video conferencing designed to empower freedom of speech, press freedom, and human rights advocacy through secure, accessible communication.

![License](https://img.shields.io/badge/license-MIT-green)
![WebRTC](https://img.shields.io/badge/WebRTC-enabled-purple)

---

## 🌟 Mission

Call Space provides secure, self-hostable communication for journalists, activists, and communities worldwide. Built on VDO.Ninja architecture, optimized for low-bandwidth rural areas.

## ✨ Key Features

- 🔒 **True P2P** - Direct connections, no server storage
- 📶 **Low-Bandwidth** - Optimized 240p-720p presets  
- 🎥 **Multi-Party** - Support up to 8 participants
- 🖥️ **Screen Sharing** - Share presentations
- 🎬 **Recording** - Save sessions locally
- 💬 **Chat Backup** - Text when video fails
- 🌐 **Self-Hostable** - Complete control
- 🎨 **Modern UI** - Beautiful space-themed design

## 🚀 Quick Start

```bash
git clone https://github.com/YOUR-USERNAME/callspace.git
cd callspace
npm install
npm start
```

Open `index.html` in your browser at `http://localhost:8080`

## 📖 Usage

**Create Room:**  
1. Click "🚀 Start Stream"
2. Share your Room ID with participants
3. They join using your Room ID

**Join Room:**  
1. Enter Room ID in "Join Remote Room"
2. Click "🔗 Connect to Guest"

**URL Parameters (VDO.Ninja Style):**
```
?room=ABC123&quality=medium&password=secret
```

## 🎨 Quality Presets

| Preset | Resolution | Bitrate | Best For |
|--------|-----------|---------|----------|
| Low | 240p | 200 kbps | Rural 2G/3G |
| Medium | 360p | 500 kbps | 3G/4G |
| High | 480p | 1 Mbps | Good 4G |
| HD | 720p | 2 Mbps | 4G/5G/Fiber |

## ⚙️ Deployment

### Docker
```bash
docker build -t callspace .
docker run -d -p 8888:8888 callspace
```

### Heroku
```bash
heroku create callspace-app
git push heroku main
```

### Your Own Server
```bash
# Install Node.js and dependencies
npm install

# Start with PM2
npm install -g pm2
pm2 start signaling-server.js --name callspace
pm2 startup
pm2 save
```

See **DEPLOYMENT.md** for detailed instructions.

## 🛡️ Security

- Always use HTTPS in production
- Enable room passwords for sensitive calls
- Self-host for maximum privacy  
- No data collection or tracking

## 🖥️ OBS Studio Integration

Add as **Browser Source** in OBS:
- URL: `http://localhost:8080/index.html`
- Width: 1920, Height: 1080

Perfect for live streaming interviews and broadcasts!

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open Pull Request

## 📝 License

MIT License - see [LICENSE](LICENSE) for details.

## 🙏 Acknowledgments

- Architecture inspired by [VDO.Ninja](https://vdo.ninja)
- Built with [WebRTC](https://webrtc.org/)
- Fonts: Orbitron, JetBrains Mono

---

## 🗺️ Roadmap

- [x] Core P2P video/audio
- [x] Multi-party support (8 people)
- [x] Screen sharing
- [x] Local recording
- [x] Text chat backup
- [x] Modern space-themed UI
- [ ] End-to-end encryption
- [ ] Virtual backgrounds
- [ ] Mobile apps (iOS/Android)
- [ ] Whiteboard collaboration
- [ ] Multi-language support

---

**Built with ❤️ for freedom of speech worldwide** 🌍

*Empowering journalists, activists, and communities to communicate securely across the universe.*
