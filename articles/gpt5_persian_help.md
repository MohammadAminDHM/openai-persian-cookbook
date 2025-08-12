# راهنمای استفاده از GPT-5 در Cookbook

این سند راهنمایی کوتاه برای استفاده از مدل **GPT-5** در مثال‌های این مخزن ارائه می‌دهد و نحوهٔ پیکربندی اولیه و اجرای یک درخواست ساده را توضیح می‌کند.

## شروع سریع

1. در وب‌سایت [OpenAI](https://platform.openai.com) حساب کاربری بسازید.
2. کلید API خود را از داشبورد دریافت کرده و آن را در متغیر محیطی `OPENAI_API_KEY` قرار دهید:

   **Linux / macOS**
   ```bash
   export OPENAI_API_KEY="کلید_شما"
   ```

   **Windows (PowerShell)**
   ```powershell
   setx OPENAI_API_KEY "کلید_شما"
   ```

3. در صورت نیاز، کتابخانهٔ `openai` را نصب کنید:

```bash
pip install openai
```

## ارسال یک درخواست نمونه

در اینجا یک نمونهٔ ساده برای ارسال پیام به مدل GPT-5 آورده شده است. کافی است فایل زیر را با نام `sample.py` ذخیره کرده و پس از تنظیم کلید API، آن را اجرا کنید:

```python
from openai import OpenAI

client = OpenAI()

response = client.chat.completions.create(
    model="gpt-5",
    messages=[{"role": "user", "content": "سلام!"}],
)

print(response.choices[0].message["content"])
```

```bash
python sample.py
```

## منابع بیشتر

برای مثال‌های بیشتر، به پوشهٔ `examples/gpt-5` سر بزنید که شامل نوت‌بوک‌های آموزشی اضافی است.
