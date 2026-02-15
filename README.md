# VIN Extraction API - Render Hosting

## 🚀 النشر على Render (مجاني)

### الخطوات:

1. **أنشئ حساب على Render:**
   - اذهب إلى https://render.com
   - سجل دخول بـ GitHub

2. **أنشئ GitHub Repo:**
   - اذهب إلى https://github.com/new
   - اسم المستودع: `vin-extraction-api`
   - اجعله Public

3. **ارفع الملفات:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/YOUR_USERNAME/vin-extraction-api.git
   git push -u origin main
   ```

4. **انشر على Render:**
   - في Render، انقر "New +" → "Web Service"
   - اربط بـ GitHub repo
   - اختر `vin-extraction-api`
   - اضبط:
     - **Runtime:** Python 3
     - **Build Command:** `pip install -r requirements.txt`
     - **Start Command:** `gunicorn server:app -b 0.0.0.0:10000`
   - انقر "Create Web Service"

5. **انتظر التثبيت** (2-3 دقائق)

6. **احصل على الرابط:**
   - سيكون API على: `https://vin-extraction-api.onrender.com`

---

## 📊 API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/` | GET | معلومات API |
| `/api/health` | GET | فحص الحالة |
| `/api/vin/extract` | POST | استخراج VIN |
| `/api/vin/verify` | POST | التحقق البشري |

---

## 🧪 اختبار

```bash
curl -X POST https://vin-extraction-api.onrender.com/api/vin/extract \
  -F "file=@image.jpg"
```

---

## ⚠️ ملاحظات

- الخطة المجانية تنام بعد 15 دقيقة من عدم الاستخدام
- أول طلب بعد النوم قد يستغرق 30-60 ثانية للاستيقاظ
- للإنتاج، استخدم خطة مدفوعة
