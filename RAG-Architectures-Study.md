# Top 5 RAG Architectures — دراسة شاملة

> المصدر: إنفوجرافيك من Brij Kishore Pandey (@brijpandeyji)
>
> تاريخ: 2026

---

## نظرة عامة

5 بنى معمارية لـ Retrieval-Augmented Generation (RAG) يجب معرفتها في 2026. RAG هو نظام يزوّد LLMs ببيانات خارجية لتحسين دقة الإجابات.

---

## 01 — Hybrid RAG 🔀

> "Dense vectors meet sparse keywords."

**الفكرة:** جمع البحث الكثيف (دلالي) مع البحث المتناثر (كلمات مفتاحية).

**التدفق:**
```
Query
  ├─ مسار Dense: Embedding Model → Vector DB → Dense Results
  └─ مسار Sparse: BM25 Index → Sparse Results
        ↓
  Reciprocal Rank Fusion (RRF)
        ↓
  Top-K Chunks
        ↓
  LLM → Answer
```

**الميزة:** يجمع أفضل ما في العالمين — الدقة الدلالية + الدقة الحرفية.

---

## 02 — GraphRAG 🕸️

> "Answers live in the relationships."
> "nodes = entities, edges = relationships"

**الفكرة:** استخراج كيانات وعلاقات من Knowledge Graph.

**التدفق:**
```
Query → Entity Extractor
          ↓
   Knowledge Graph
   ├─ Nodes: Company, Person, Location, Project, Technology
   └─ Edges: works_at, located_in, works_on, related_to
          ↓
   Subgraph Retrieval
          ↓
   Community Summaries
          ↓
   LLM → Answer
```

**الميزة:** يفهم العلاقات المعقدة بين الكيانات — مثالي للأسئلة متعددة القفزات.

---

## 03 — Agentic RAG 🤖

> "Retrieval becomes a plan, not a step."

**الفكرة:** وكيل مستقل يخطط لاستراتيجية البحث.

**التدفق:**
```
Query → Planner Agent
          ├─ Vector Search Tool
          ├─ Web Search Tool
          └─ SQL Database Tool
                ↓
          Reasoner Agent
                ↓
          (agent loops until confident)
                ↓
          Final Answer
```

**الميزة:** الاسترجاع خطة كاملة مش خطوة — الوكيل يقرر أي أداة ومتى يرجع.

---

## 04 — Corrective RAG (CRAG) ✅

> "Grade the retrieval before you trust it."

**الفكرة:** تقييم جودة الاسترجاع قبل إرساله للـ LLM.

**التدفق:**
```
Query → Retriever → Retrieved Docs → Evaluator/Grader
                                        ├─ صحيح ← LLM → Answer
                                        ├─ غامض ← Query Rewriter → LLM → Answer
                                        └─ خطأ ← Web Search Fallback → LLM → Answer
```

**الميزة:** تصحيح ذاتي — لو الاسترجاع ضعيف، يصححه أو يرجع للويب.

---

## 05 — Multimodal RAG 🎨

> "One index across text, images, and tables."

**الفكرة:** فهرس موحد لكل أنواع البيانات.

**التدفق:**
```
Text Chunks ─┐
Images/Charts ─┼─ Shared Multimodal Embedding Model (CLIP/ColPali)
Tables ──────┘
                    ↓
            Unified Vector Index
                    ↓
              Retrieval
                    ↓
     Multimodal LLM (vision + text)
                    ↓
                Answer
```

**الميزة:** يعالج النص والصور والجداول في آن واحد — موحد.

---

## مقارنة سريعة

| البنية | نقطة القوة | نقطة الضعف | أفضل استخدام |
|--------|-----------|-----------|-------------|
| **Hybrid RAG** | دقة عالية (دلالي + حرفي) | تعقيد أعلى | بحث مؤسسي دقيق |
| **GraphRAG** | فهم العلاقات | بناء الـ Knowledge Graph مكلف | أسئلة متعددة القفزات |
| **Agentic RAG** | مرونة وذكاء | بطء (حلقات تفكير) | مهام معقدة متعددة المصادر |
| **CRAG** | تصحيح ذاتي | يعتمد على جودة المقيم | بيئات غير موثوقة |
| **Multimodal RAG** | شامل لكل البيانات | يحتاج نماذج متخصصة | مستندات مختلطة (PDF, PPT) |

---

## الدروس المستفادة

1. **لا تثق بالاسترجاع مباشرة** — CRAG يعلمنا نقيّم قبل نسلّم للـ LLM
2. **العلاقات أهم من البيانات** — GraphRAG يستخرج المعنى من الروابط
3. **الوكيل أذكى من الخطوة الواحدة** — Agentic RAG يحول الاسترجاع لخطة
4. **النص مش كل شي** — Multimodal RAG يوحّد النص والصورة والجدول
5. **الكثيف + المتناثر > واحد منهم** — Hybrid RAG يثبت أن الدمج أفضل

---

> دراسة من إنفوجرافيك Brij Kishore Pandey — 21 يونيو 2026
