# CLAUDE.md — प्रोजेक्ट संदर्भ (Project Context for Claude Code)

यह फाइल Claude Code इस प्रोजेक्ट को खोलते ही अपने-आप पढ़ता है। इसमें वो सब कुछ है जो आगे बदलाव करने के लिए जानना ज़रूरी है।

## प्रोजेक्ट क्या है

पं. रवि कांत मिश्रा (भाजपा नेता, ब्रज सेवक, मथुरा-वृंदावन पूर्व विधानसभा प्रत्याशी) के लिए एक single-page परिचय वेबसाइट। यह पूरी तरह हिंदी में है — कोई भी नया content भी हिंदी में ही लिखा जाना चाहिए, अंग्रेज़ी में नहीं।

## Tech Stack

- **Plain HTML + CSS + vanilla JS** — कोई framework, build tool या bundler नहीं है। `index.html` एक ही self-contained फाइल है जिसमें `<style>` और `<script>` दोनों inline हैं।
- कोई npm/package.json नहीं है। सीधे browser में `index.html` खोलकर देखा जा सकता है।
- Fonts Google Fonts CDN से लोड होते हैं: `Tiro Devanagari Hindi` (headings) और `Noto Sans Devanagari` (body text)।
- Images `images/` folder में local रूप से रखी गई हैं — कोई external/Wikipedia URL इस्तेमाल न करें, हमेशा local files ही use करें।

## Files

```
index.html          → पूरी वेबसाइट (structure + CSS + JS सब इसी में)
images/
  ravi-mishra.jpg          → हीरो सेक्शन फोटो
  ravi-mishra-banner.png   → परिचय सेक्शन का official बैनर (नाम व पद के साथ)
  narendra-modi.jpg        → नेतृत्व सेक्शन
  mahesh-sharma.jpg        → नेतृत्व सेक्शन (सांसद, गौतम बुद्ध नगर)
  pankaj-singh.jpg         → नेतृत्व सेक्शन (विधायक, नोएडा)
CONTENT.md           → WhatsApp ग्रुप से निकाला गया सारा source content (bio, quotes, timeline)
README.md            → Setup और deployment के निर्देश
```

## Design System (मत बदलें बिना पूछे)

CSS variables `:root` में `index.html` की शुरुआत में defined हैं:

| Variable | Hex | उपयोग |
|---|---|---|
| `--saffron` | `#FF6B00` | Primary CTA, accents |
| `--orange` | `#FF9933` | Hover states |
| `--navy` | `#0D1B3E` | Dark sections background (nav, hero, seva, sampark) |
| `--gold` | `#C9A84C` | Headings on dark bg, borders |
| `--cream` | `#FFF8EE` | Light section backgrounds |

Typography: headings = `Tiro Devanagari Hindi` serif, body = `Noto Sans Devanagari`. इसे mix न करें।

## नाम — बहुत ज़रूरी

सही नाम **हमेशा** है: **पं. रवि कांत मिश्रा**
पूरा designation: **वरिष्ठ भाजपा नेता · वरिष्ठ समाजसेवी · पूर्व विधायक प्रत्याशी · मथुरा-वृंदावन (84 विधानसभा)**

⚠️ **"पूर्व विधायक प्रत्याशी" (Ex MLA Candidate)** — "पूर्व विधायक" (Ex MLA) कभी नहीं लिखें। वे चुनाव में खड़े हुए थे, विधायक चुने नहीं गए थे।

❌ गलत: "रवि मिश्र", "Ravi Mishra Mahagun" (यह सिर्फ़ उनका WhatsApp display name था, वेबसाइट पर कभी इस्तेमाल नहीं करना)

## Content नियम

1. **कोई absolute वादा न करें** — "कोई व्यक्ति X से वंचित न रहे" जैसी categorical guarantees मत लिखें। इसके बदले "प्रयास करता है", "की दिशा में काम करता है" जैसी भाषा use करें। यह पहले एक बार ठीक किया गया है (Noeda Lokmanch वाला paragraph) — यही पैटर्न आगे भी maintain रखें।
2. सारी नई content **हिंदी में** होनी चाहिए, कोई अंग्रेज़ी section नहीं।
3. कोई भी raw quote/detail directly WhatsApp चैट से copy-paste मत करें — पहले `CONTENT.md` में check करें कि क्या पहले से extracted/verified है।
4. Real, real-world political figures (मोदी जी, योगी जी आदि) के बारे में facts लिखते समय careful रहें — केवल वही cite करें जो WhatsApp source data में मौजूद है, अपनी तरफ़ से कुछ न जोड़ें।

## Sections (मौजूदा क्रम — id attribute से match करें)

1. `#hero` — नाम, फोटो, tagline, stats
2. `#parichay` — About/Bio, banner photo
3. `#drishti` — Vision cards (6 cards, developmental priorities)
4. `#seva` — Social work (Noida Lokmanch health project आदि)
5. `#neta` — Leadership figures (Modi, Mahesh Sharma, Pankaj Singh)
6. `#sampark-jan` — Outreach timeline (major meetings)
7. `#gallery` — Photo gallery grid (अभी placeholder SVG icons हैं, real photos add होनी बाकी हैं)
8. `#sampark` — Contact form (mailto-based) + Facebook link

## Pending / Known TODOs

- [ ] `#gallery` section में अभी placeholder icons हैं — real event photos add करनी हैं जब user उपलब्ध कराए
- [ ] Contact form अभी सिर्फ़ `mailto:` खोलता है (`ravi019971@gmail.com` की तरफ़ — verified) — कोई backend नहीं है। अगर real form submission चाहिए (Formspree, EmailJS आदि) तो user से confirm करें पहले।
- [ ] कोई analytics/tracking नहीं लगाया गया है

## Facebook

आधिकारिक पेज: https://www.facebook.com/ravimishra2121
फोटो एल्बम: https://www.facebook.com/ravimishra2121/photos

## काम करने का तरीका

- कोई भी बदलाव करने से पहले `CONTENT.md` देखें कि उपलब्ध source data में क्या है
- नई content बनाते समय ऊपर दिए गए content नियम (especially point 1 — no absolute promises) का पालन करें
- Design tokens/fonts बदलने से पहले user से पूछें
- हर बदलाव के बाद `index.html` को browser में खोलकर visually verify करें (या screenshot लें)
