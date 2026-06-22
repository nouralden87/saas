# تحسين إعدادات Hermes — توصيات AI Labs

**المصدر:** [AI Labs — Hermes Configuration Guide](https://youtu.be/nN6DZi_fiSo)  
**القناة:** AI Labs (Nous Research ecosystem)  
**التاريخ:** يونيو 2026

---

## الفئة ١: حدود السياق والمخرجات

| الإعداد | الافتراضي | التوصية | السبب |
|---------|----------|---------|-------|
| `tool_output.max_bytes` | 50,000 | **100,000+** | سحب مخرجات أطول من الأدوات (مراقبة الاختبارات، سجلات) |
| `file_read_max_chars` | — | **5,000 سطر** | لقراءة ملفات كبيرة (وثائق، قاعدة معرفة) |
| `tool_output.max_line_length` | 2,000 | **5,000+** | للفقرات الطويلة في Markdown بدون تقطيع |
| `compression.threshold` | 0.50 | **0.75** | استخدام 75% من نافذة السياق قبل الضغط (مثل Codex) |
| `compression.target_ratio` | 0.20 | **0.20–0.80** | نسبة المحادثة غير المضغوطة بعد الضغط |
| `memory.memory_char_limit` | 2,200 | حسب الحاجة | للذاكرة الدائمة |
| `memory.user_char_limit` | 1,375 | حسب الحاجة | لملف المستخدم |

### أمر التطبيق:
```bash
hermes config set tool_output.max_bytes 100000
hermes config set tool_output.max_line_length 5000
hermes config set compression.threshold 0.75
```

---

## الفئة ٢: الوكلاء الفرعيون (Sub-agents)

| الإعداد | الافتراضي | التوصية | السبب |
|---------|----------|---------|-------|
| `delegation.max_concurrent_children` | 3 | **5** | تسريع المشاريع الكبيرة (انتبه: يستهلك توكنز أكثر) |
| `delegation.max_spawn_depth` | 1 | **2+** | السماح للوكلاء الفرعيين بإنشاء وكلاء أعمق |
| `delegation.subagent_auto_approve` | false | **true** | منع توقف الوكلاء الفرعيين عند طلب الأذونات |

### أمر التطبيق:
```bash
hermes config set delegation.max_concurrent_children 5
hermes config set delegation.max_spawn_depth 2
hermes config set delegation.subagent_auto_approve true
```

---

## الفئة ٣: توفير التكاليف

### نماذج مساعدة (Auxiliary Models)
- تعيين نماذج أرخص للمهام الخلفية (رؤية، ضغط، بحث ويب)
- إذا تركت فارغة: Hermes يستخدم أرخص نموذج متاح (مثلاً Gemini Flash على OpenRouter)
- وفر تكاليف كبيرة بعدم إهدار النموذج الرئيسي على مهام بسيطة

```bash
hermes config set auxiliary.vision.provider nvidia
hermes config set auxiliary.vision.model meta/llama-3.2-11b-vision-instruct
```

### مستوى التفكير (Reasoning Effort)
- تعيين `reasoning_effort` إلى `low` أو `minimum` لتقليل استهلاك التوكنز
- يمكن إيقاف التفكير تماماً

---

## الفئة ٤: سير العمل

### أوامر سريعة (Quick Commands)
- **exec**: تشغل أمر طرفية وتُدخل مخرجاته في السياق
- **alias**: اختصار لأوامر موجودة (مثلاً `c` بدل `compress`)

### نقاط التفتيش (Checkpoints)
```bash
hermes config set checkpoints.enabled true
```
- حفظ حالة الملفات عند نقطة زمنية
- التراجع عند كسر شيء `/rollback`

### إشعارات العمليات الخلفية
- `background process notifications` → `all` لإشعارات كل شيء

### الوضع الآمن (YOLO Mode)
```bash
hermes --yolo
```
- تجاوز طلبات الموافقة (مثل `--dangerously-skip-permissions` في Claude)

### تجاهل إعدادات المستخدم (لتصحيح الأخطاء)
```bash
hermes --ignore-user-config
```
- تشغيل Hermes بدون أي إعدادات مخصصة لعزل المشاكل

---

## توصيات فورية لتطبيقها

```bash
# السياق
hermes config set tool_output.max_bytes 100000
hermes config set compression.threshold 0.75

# الوكلاء الفرعيون
hermes config set delegation.max_concurrent_children 5
hermes config set delegation.max_spawn_depth 2

# التوفير
# (البصر مضبوط حالياً على NVIDIA)
```

---

## ملاحظات

- كل التغييرات تطبق على الملف الشخصي النشط (active profile)
- لاستخدام عدة ملفات شخصية: `hermes profile create`
- النماذج المساعدة توفر تكاليف هائلة على المدى الطويل
- كل تغيير `max_concurrent_children` يزيد التكاليف (انتبه للرصيد)
