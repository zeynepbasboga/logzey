# 🔐 LogZey

**Lightweight, cloud-native security log analyzer** designed for **home users and small businesses**.  
Built with AWS Lambda, API Gateway, SNS, and Terraform — LogZey detects suspicious login attempts and sends real-time alerts.

---

## 🚀 Features

- ✅ Parses and analyzes authentication logs (e.g. SSH failed attempts)  
- 🌍 Performs GeoIP lookup for suspicious IP addresses using external API  
- 📬 Sends alert e-mails via Amazon SNS  
- ⚙️ Fully deployable with Terraform  
- ☁️ Serverless – No infrastructure to manage  

---

## 🏗 Architecture

> ![](https://raw.githubusercontent.com/zeynepbasboga/logzey/refs/heads/main/assets/Architecture.png)

---

## ⚡ Quick Start

1. **Clone the repo**
```bash
git clone https://github.com/yourusername/logzey.git
cd logzey
```

2. **Create variable file**:
```hcl
# myvars.auto.tfvars
alert_email = "your-email@example.com"
```

3. **Deploy with Terraform**
```bash
cd terraform-files
terraform init
terraform apply
```

4. **Approve SNS subscription** from your email inbox

---

## 📡 API Usage

```bash
curl -X POST https://your-api-id.execute-api.us-east-1.amazonaws.com/logs \
  -H "Content-Type: application/json" \
  --data-binary @logzey_v2_logs.json
```

**Sample log:**
```json
{
  "ip": "85.239.33.141",
  "status": "failed",
  "timestamp": "2025-06-18T12:00:00",
  "port": "40038"
}
```

---

## 📬 Sample Alert Email

```
🚨 Suspicious Login Detected!

IP Address: 196.251.67.**
Location: Amsterdam, Unknown
Time: 2025-06-18T09:13:41 UTC

This IP triggered 5+ failed login attempts in under 1 minute.
```

---

## 🧰 Built With

- AWS Lambda  
- API Gateway  
- SNS  
- Terraform  
- Python 3.12  

---

## 🤝 Contributing

Feel free to fork and PR 🙌  
Bug fixes, improvements, suggestions are welcome.

---

## 📄 License

MIT License – see `LICENSE` file.
