# دروس مستفادة من جلسات البحث — يونيو 2026

**خلاصة كل ما تعلمته من دراستك للمحتوى. هذا ما سيغير أدائي.**

---

## ١. البنية المعمارية — لا تبني أكبر، بل انسق أذكى

- **Sakana Fugu × Trinity**: موديل 7B صغير ينسق بين عمالقة → يتفوق عليهم
- **MCP → A2A**: المستقبل ليس وكيلاً واحداً، بل فريق وكلاء متخصصين
- **التطبيق**: delegate_task + Kanban = Trinity خاصة بنا

## ٢. التوفير والتحسين — كل توكن له ثمن

- **Auxiliary models**: مهام الرؤية والضغط والبحث → نماذج رخيصة (NVIDIA Llama 3.2 Vision)
- **compression.threshold = 0.75**: استخدم 75% من السياق قبل الضغط
- **tool_output.max_bytes = 100k**: لا تفقد مخرجات مهمة
- **delegation children = 5**: سرّع المشاريع الكبيرة

## ٣. البصر — NVIDIA شغال، OpenCode لا

- `AUXILIARY_VISION_PROVIDER=nvidia`
- `AUXILIARY_VISION_MODEL=meta/llama-3.2-11b-vision-instruct`
- env vars تتجاوز config.yaml — تحتاج gateway restart
- OpenCode.ai لا يدعم vision (كل شي عبر DeepSeek)

## ٤. الأمان — الـ AI لن يخبرك بالمشاكل

- ٥ ثغرات يغفلها AI عند بناء SaaS
- Testing > Coding (مهارة المصحح أهم من مهارة الكاتب)
- البرومبت الصحيح = أمان + معمارية + تكلفة

## ٥. المصادر المفتوحة — لا تدفع لشيء مجاني

- LibreChat (39k⭐) = كل موديلات AI في تطبيق واحد
- Camofox (7k⭐) = متصفح متخفي للبوتات → hak
- Hyperframes (29k⭐) = HTML → فيديو
- cc-switch (106k⭐) = **يدعم Hermes رسمياً**

## ٦. Engineering as Marketing

- ابنِ أدوات مجانية → تجذب مستخدمين → يكتشفون منتجك المدفوع
- gittrend.io يغطي المشاريع الرائجة → فرصة انتشار
- محتوى عربي تقني عليه طلب (DevOps، AI Building)

## ٧. الدروس التقنية من Hermes

- `hermes gateway restart` من خارج الجلسة لتطبيق تغييرات config
- env vars > config.yaml في العملية الشغالة
- `read -s` للإدخال السري للمفاتيح

---

## ما سأفعله مختلفاً من الآن

1. **قبل أي مهمة**: فكر في التنسيق (Orchestration) قبل التنفيذ — Trinity
2. **كل استهلاك توكن**: احسب التكلفة — استخدم auxiliary models للمهام البسيطة
3. **بعد كل خطوة**: تحقق — Verifier قبل الانتقال
4. **المحتوى المرئي**: استخدم NVIDIA vision مباشر، لا تضيع وقت على OpenCode للصور
5. **الحفظ**: كل معرفة تكتسب → احفظها فوراً في saas/hak
