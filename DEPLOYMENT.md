# دليل النشر - مشروع كيكه سندرين بيوتي 🚀

## النشر على Vercel (الطريقة الموصى بها)

### الخطوات:

1. **رفع الكود إلى GitHub**
   \`\`\`bash
   git init
   git add .
   git commit -m "Initial commit: Keeka Sandrine Beauty website"
   git branch -M main
   git remote add origin https://github.com/yourusername/keeka-sandrine-beauty.git
   git push -u origin main
   \`\`\`

2. **ربط المشروع بـ Vercel**
   - اذهب إلى [vercel.com](https://vercel.com)
   - اضغط "New Project"
   - اختر المستودع من GitHub
   - اضغط "Deploy"

3. **إضافة متغيرات البيئة**
   في لوحة تحكم Vercel:
   - اذهب إلى Settings > Environment Variables
   - أضف المتغيرات التالية:
   \`\`\`
   NEXT_PUBLIC_SUPABASE_URL = https://nulsebapvygnnskageip.supabase.co
   NEXT_PUBLIC_SUPABASE_ANON_KEY = eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
   NEXT_PUBLIC_WHATSAPP_NUMBER = 201556133633
   \`\`\`

4. **إعادة النشر**
   - اضغط "Redeploy" لتطبيق المتغيرات الجديدة

## إعداد قاعدة البيانات Supabase

### الخطوات:

1. **إنشاء مشروع جديد**
   - اذهب إلى [supabase.com](https://supabase.com)
   - اضغط "New Project"
   - اختر اسم المشروع: "keeka-sandrine-beauty"

2. **تشغيل سكريبت إنشاء الجداول**
   - اذهب إلى SQL Editor في Supabase
   - انسخ محتوى ملف `scripts/01_create_orders_table.sql`
   - شغل السكريبت

3. **تفعيل Row Level Security**
   \`\`\`sql
   ALTER TABLE orders ENABLE ROW LEVEL SECURITY;
   
   -- السماح بالقراءة والكتابة للجميع (للتطوير)
   CREATE POLICY "Enable all operations for orders" ON orders
   FOR ALL USING (true) WITH CHECK (true);
   \`\`\`

## التحقق من النشر

### اختبار الوظائف:
- ✅ تحميل الصفحة الرئيسية
- ✅ عرض صور المنتج
- ✅ تسجيل طلب جديد
- ✅ إرسال رسالة واتساب
- ✅ الوصول للوحة الإدارة (7 نقرات)
- ✅ عرض الطلبات في لوحة الإدارة

### اختبار الاستجابة:
- 📱 موبايل (375px)
- 📱 تابلت (768px)
- 💻 ديسكتوب (1024px)

## النشر على منصات أخرى

### Netlify
\`\`\`bash
npm run build
# رفع مجلد out/ إلى Netlify
\`\`\`

### Hosting تقليدي
\`\`\`bash
npm run build
npm run export
# رفع مجلد out/ إلى الخادم
\`\`\`

## نصائح مهمة

1. **الأمان**: لا تشارك مفاتيح API الخاصة
2. **النسخ الاحتياطي**: احتفظ بنسخة من قاعدة البيانات
3. **المراقبة**: تابع الأخطاء في Vercel Analytics
4. **التحديثات**: حدث المكتبات بانتظام

## استكشاف الأخطاء

### مشاكل شائعة:
- **خطأ في قاعدة البيانات**: تأكد من تشغيل سكريبت SQL
- **صور لا تظهر**: تأكد من رفع الصور في مجلد public/
- **واتساب لا يعمل**: تأكد من رقم الهاتف صحيح

### سجلات الأخطاء:
- Vercel: Functions > View Logs
- Supabase: Logs & Analytics
- Browser: Developer Tools > Console

---

**نشر سعيد! 🎉**
