# Sakana Fugu — منسق الموديلات الياباني

**المصدر:** [@getintoai](https://www.instagram.com/getintoai) (موثق ✓) — 22 يونيو 2026  
**الرابط:** https://www.instagram.com/p/DZ5s9zVjENI/  
**التفاعل:** ❤️ 255 | 💬 4

---

## الخبر

مختبر AI ياباني (**Sakana AI**) يعلن عن نظام **Fugu** — منسق ذكي يوزع المهام على أفضل الموديلات المتاحة:

> "Instead of being a single massive model, Fugu acts as a coordinator. You send one request, and it decides which frontier models are best suited for different parts of the task. It then combines their outputs into a single response designed to outperform what any one model could produce alone."

## الفريق

أسسه **أحد المؤلفين المشاركين في ورقة Transformer الأصلية** — البحث الذي أسس للذكاء الاصطناعي الحديث.

## النتائج (SWE-Bench Pro)

| النظام | النتيجة |
|--------|---------|
| **Fugu Ultra** | **73.7** |
| Claude Opus 4.8 | 69.2 |
| GPT-5.5 | 58.6 |

## المعمارية

- ليس موديلاً واحداً — بل **منسق (Orchestrator)**
- يختار أفضل موديل لكل جزء من المهمة
- يجمع المخرجات في استجابة واحدة متفوقة
- مرن: يمكن تبديل الموديلات حسب التسعير والتوفر والقيود التنظيمية

## الاقتباس الرئيسي

> "The future of AI may not belong to a single model. It may belong to systems that know how to use many models together."

## الدروس المستفادة

1. **المستقبل للتنسيق لا للحجم** — Mixture of Agents ≠ MoE (خبراء داخل موديل واحد)
2. **تفوق على موديلات أكبر** — دمج مخرجات متعددة > موديل واحد ضخم
3. **الفريق الياباني** أثبت أن الهندسة المعمارية أهم من القوة الحاسوبية
4. **مرونة استراتيجية**: لا تعتمد على مزود واحد

## صلة بمشاريعنا

- **Hermes delegation**: نفس الفكرة — تفويض المهام لوكلاء متعددين
- **A2A Protocol** (من منشور n8nstack): هذا تطبيق عملي لفلسفة Agent-to-Agent
- **الاستراتيجية**: بدل شراء موديل واحد غالي، نسق بين عدة موديلات رخيصة/مجانية
- **فكرة مشروع**: "Hermes Orchestrator" — منسق يوزع المهام بين DeepSeek/Claude/GPT حسب نوع المهمة

---

## مراجع

- منشور getintoai: https://www.instagram.com/p/DZ5s9zVjENI/
- Sakana AI: https://sakana.ai
