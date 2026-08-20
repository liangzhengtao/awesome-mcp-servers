[English](README.md) | [中文](README.zh.md) | [日本語](README.ja.md) | [Français](README.fr.md) | [Español](README.es.md) | [العربية](README.ar.md) | [한국어](README.ko.md) | [Português](README.pt.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)

<div dir="rtl" align="center">

<img src=".banner.svg" width="100%" alt="banner">

</div>


<div dir="rtl" align="center">

# 🚀 خوادم MCP الرائعة

**نظام MCP البيئي لـ Cursor و Claude Code و Kimi Code. ملف إعداد واحد. قدرات حقيقية.**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Servers](https://img.shields.io/badge/Servers-9-blue)](#servers)

<br/>

[ما هو MCP؟](#what-is-mcp) • [الخوادم](#servers) • [البدء السريع](#quick-start) • [الفئات](#categories) • [الأسئلة الشائعة](#faq) • [المساهمة](CONTRIBUTING.md)

</div>

---

## ما هو MCP؟

**بروتوكول سياق النموذج (MCP)** هو معيار مفتوح يسمح لمساعدي البرمجة بالذكاء الاصطناعي بالتواصل مع الأدوات وقواعد البيانات والخدمات الخارجية. بدلاً من عمل ذكائك الاصطناعي في عزلة، يمنحه MCP قدرات خارقة — يمكنه الاستعلام عن قاعدة بياناتك، وإدارة مستودعاتك، وتصفح الويب، وأكثر من ذلك بكثير.

---

## قبل وبعد

<table>
<tr>
<td width="50%" valign="top">

### ❌ بدون MCP

```
أنت: "تحقق من Postgres لدينا لعدد المستخدمين"
AI: "لا يمكنني الوصول إلى قاعدة بياناتك."

أنت: "انظر إلى آخر المشكلات على GitHub"
AI: "ليس لدي صلاحية الوصول إلى GitHub."

أنت: "ماذا تقول وثائق React عن hooks؟"
AI: "قد تكون بيانات تدريبي قديمة."
```

</td>
<td width="50%" valign="top">

### ✅ مع MCP

```
أنت: "تحقق من Postgres لدينا لعدد المستخدمين"
AI: → يسأل قاعدة البيانات → "لديك 14,832 مستخدم."

أنت: "انظر إلى آخر المشكلات على GitHub"
AI: → يقرأ المشكلات → "3 أخطاء مفتوحة، 2 طلبات ميزة."

أنت: "ماذا تقول وثائق React عن hooks؟"
AI: → يجلب الوثائق الحية → "إليك آخر API..."
```

</td>
</tr>
</table>

**MCP يحوّل ذكائك الاصطناعي من مجرد إكمال تلقائي ذكي إلى زميل هندسي متكامل.**

---

## الخوادم

| # | الخادم | الفئة | الوصف | الحزمة |
|---|--------|----------|-------------|---------|
| 1 | [Filesystem](servers/filesystem.md) | 📁 ملفات | قراءة وكتابة وإدارة الملفات المحلية | `@modelcontextprotocol/server-filesystem` |
| 2 | [GitHub](servers/github.md) | 🔧 تطوير | المستودعات، المشكلات، طلبات السحب، والبحث في الكود | `@modelcontextprotocol/server-github` |
| 3 | [PostgreSQL](servers/postgres.md) | 🗄️ قواعد البيانات | الاستعلام عن قواعد بيانات PostgreSQL واستكشافها | `@modelcontextprotocol/server-postgres` |
| 4 | [Redis](servers/redis.md) | 🗄️ قواعد البيانات | التخزين المؤقت، النشر/الاشتراك، وعمليات القيمة-المفتاح | `@modelcontextprotocol/server-redis` |
| 5 | [Web Search](servers/web-search.md) | 🌐 ويب | البحث في الويب باستخدام Brave أو Google | `@modelcontextprotocol/server-brave-search` |
| 6 | [Memory](servers/memory.md) | 🧠 معرفة | الذاكرة الدائمة ورسم المعرفة البياني | `@modelcontextprotocol/server-memory` |
| 7 | [Puppeteer](servers/puppeteer.md) | 🌐 ويب | أتمتة المتصفح وشبكة الويب | `@modelcontextprotocol/server-puppeteer` |
| 8 | [Slack](servers/slack.md) | 💬 اتصالات | إرسال الرسائل وإإدارة القنوات | `@modelcontextprotocol/server-slack` |
| 9 | [Context7](servers/context7.md) | 📚 توثيق | وثائق المكتبات المحدثة | `@upstash/context7-mcp` |

---

## الفئات

| الفئة | الخوادم | الوصف |
|----------|---------|-------------|
| [🔧 تطوير](by-category/development.md) | GitHub | الكود، المستودعات |
| [🗄️ قواعد بيانات](by-category/databases.md) | PostgreSQL, Redis | الاستعلام، التخزين، التخزين المؤقت |
| [💬 اتصالات](by-category/communication.md) | Slack | المراسلة |
| 📁 ملفات | Filesystem | عمليات الملفات المحلية |
| 🌐 ويب | Web Search, Puppeteer | البحث، أتمتة المتصفح |
| 🧠 معرفة | Memory, Context7 | السياق الدائم، الوثائق الحية |

---

## البدء السريع

أضف خادم MCP إلى مساعد البرمجة بالذكاء الاصطناعي في أقل من 30 ثانية.

### Cursor

1. أنشئ أو عدّل `.cursor/mcp.json` في جذر مشروعك:

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/your/project"]
    }
  }
}
```

2. أعد تشغيل Cursor. ستظهر أيقونة خادم MCP في شريط الحالة السفلي.

### Claude Code

```bash
# Add a server with one command
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem /path/to/your/project

# Verify it's running
claude mcp list
```

### Kimi Code

قم بإعداد عبر `config.toml` في دليل إعدادات Kimi Code:

```toml
[mcp_servers.filesystem]
command = "npx"
args = ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/your/project"]
```

---

## خوادم متعددة في نفس الوقت

يمكنك تكديس أكبر عدد من الخوادم حسب حاجتك:

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "."]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_xxxxxxxxxxxx"
      }
    },
    "postgres": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-postgres", "postgresql://localhost/mydb"]
    }
  }
}
```

---

## الأسئلة الشائعة

<details>
<summary><strong>ما هو MCP؟</strong></summary>

بروتوكول سياق النموذج (MCP) هو معيار مفتوح أنشأته Anthropic يحدد كيفية توصيل مساعدي الذكاء الاصطناعي بالأدوات ومصادر البيانات الخارجية. فكّر فيه كموصل عالمي للذكاء الاصطناعي — بروتوكول واحد، أي أداة.

</details>

<details>
<summary><strong>هل MCP مجاني؟</strong></summary>

نعم. MCP نفسه بروتوكول مفتوح (مرخص بـ MIT). خوادم MCP الفردية مجانية للتشغيل محليًا. قد تتطلب بعضها مفاتيح API لخدمات الطرف الثالث (مثل رمز GitHub، رمز Slack).

</details>

<details>
<summary><strong>أي مساعدي ذكاء اصطناعي يدعمون MCP؟</strong></summary>

اعتبارًا من 2026، يدعم MCP:
- **Cursor** — دعم كامل عبر `.cursor/mcp.json`
- **Claude Code** — دعم كامل عبر CLI (`claude mcp add`)
- **Kimi Code** — دعم كامل عبر `AGENTS.md` أو `config.toml`
- **Windsurf**، **Cline**، **Continue** — دعم متنامي

</details>

<details>
<summary><strong>هل خوادم MCP آمنة؟</strong></summary>

خوادم MCP تعمل محليًا على جهازك. لديها فقط الأذونات التي تمنحها لها. راجع دائمًا ما يفعله الخادم قبل إضافته. للاستخدام في الإنتاج، قيّد مسارات الملفات واستخدم اتصالات قواعد بيانات للقراءة فقط حيثما أمكن.

</details>

<details>
<summary><strong>هل يمكنني بناء خادم MCP خاص بي؟</strong></summary>

بالتأكيد. SDK الخاص بـ MCP متاح لـ [TypeScript](https://github.com/modelcontextprotocol/typescript-sdk) و [Python](https://github.com/modelcontextprotocol/python-sdk). راجع [الوثائق الرسمية](https://modelcontextprotocol.io) للبدء.

</details>

<details>
<summary><strong>كيف أستكشف خادمًا لا يعمل؟</strong></summary>

1. تأكد من تثبيت Node.js 18+ (أو وقت التشغيل المطلوب)
2. حاول تشغيل الامر يدويًا في الطرفية لرؤية الأخطاء
3. تحقق من تعيين متغيرات البيئة / مفاتيح API المطلوبة
4. أعد تشغيل مساعد الذكاء الاصطناعي بعد تغيير إعدادات MCP

</details>

---

## انظر أيضًا

| المشروع | الوصف |
|---------|-------------|
| [**awesome-ai-rules**](https://github.com/liangzhengtao/awesome-ai-rules) | 20 قاعدة برمجة AI إنتاجية |
| [**vibe-check**](https://github.com/liangzhengtao/vibe-check) | `npx vibe-check` — احسب جاهزية مشروعك للـ AI |
| [**ai-commit**](https://github.com/liangzhengtao/ai-commit) | `npx ai-commit` — AI يكتب رسائل commit لك |

## المساهمة

نحب المساهمات! راجع [CONTRIBUTING.md](CONTRIBUTING.md) لمعرفة كيفية إضافة خادم MCP جديد.

---

## الترخيص

[MIT](LICENSE) — استخدمه كما تشاء.

---

<div dir="rtl" align="center">

**بُني بـ ❤️ بواسطة مجتمع MCP**

[⬆ العودة للأعلى](#-awesome-mcp-servers)

</div>

---
