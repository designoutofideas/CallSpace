# 🚀 Call Space Deployment Guide

Complete guide for deploying Call Space to GitHub and hosting platforms.

## 📦 Quick GitHub Setup

```bash
# 1. Create repository on GitHub.com
# Name: callspace
# Public repository

# 2. Navigate to your Call Space folder
cd /path/to/callspace

# 3. Initialize and push
git init
git add .
git commit -m "Initial commit: Call Space"
git remote add origin https://github.com/YOUR-USERNAME/callspace.git
git push -u origin main
```

## 🌐 Deployment Options

### Option 1: Heroku (Recommended)

```bash
heroku login
heroku create callspace-app
echo "web: node signaling-server.js" > Procfile
git add Procfile
git commit -m "Add Procfile"
git push heroku main
```

Update `config.js`:
```javascript
signalingServer: {
    url: 'wss://callspace-app.herokuapp.com'
}
```

### Option 2: Railway.app (Easiest)

1. Visit https://railway.app
2. Deploy from GitHub repo
3. Auto-detects Node.js
4. Copy provided URL
5. Update `config.js` with URL

### Option 3: DigitalOcean/VPS

```bash
# Install Node.js
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt-get install -y nodejs nginx

# Clone and setup
git clone https://github.com/YOUR-USERNAME/callspace.git
cd callspace
npm install

# Start with PM2
sudo npm install -g pm2
pm2 start signaling-server.js --name callspace
pm2 startup
pm2 save
```

#### Nginx Configuration

```nginx
server {
    listen 80;
    server_name yourdomain.com;
    
    root /var/www/callspace;
    index index.html;
    
    location / {
        try_files $uri $uri/ /index.html;
    }
    
    location /signal {
        proxy_pass http://localhost:8888;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
    }
}
```

#### Enable HTTPS (Required)

```bash
sudo apt install certbot python3-certbot-nginx
sudo certbot --nginx -d yourdomain.com
```

## 🧪 Testing

1. Open your deployed URL
2. Click "Start Stream"
3. Open another browser/device
4. Join with Room ID
5. Test video, audio, recording

## 🔒 Security Checklist

- [ ] HTTPS enabled
- [ ] Firewall configured
- [ ] Dependencies updated
- [ ] Room passwords enabled
- [ ] Logs monitored

## 🆘 Troubleshooting

**WebSocket connection failed:**
- Verify signaling server is running
- Check config.js URL matches deployment
- Ensure firewall allows WebSocket

**Camera/mic not working:**
- Must use HTTPS (not HTTP)
- Check browser permissions
- Try different browser

## 🔄 Updating

```bash
git add .
git commit -m "Update: description"
git push origin main

# Heroku/Railway auto-deploy
# VPS: ssh in, git pull, pm2 restart callspace
```

---

**Your Call Space instance is ready to empower free speech worldwide!** 🌍
