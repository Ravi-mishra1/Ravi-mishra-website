# पं. रवि कांत मिश्रा — परिचय वेबसाइट

भारतीय जनता पार्टी नेता पं. रवि कांत मिश्रा (ब्रज सेवक, मथुरा-वृंदावन) के लिए single-page हिंदी वेबसाइट।

## Local में खोलना

कोई installation या build step नहीं चाहिए। सीधे `index.html` को किसी भी browser में डबल-क्लिक करके खोलें।

VS Code में देखने के लिए **Live Server** extension recommended है (right-click on `index.html` → "Open with Live Server"), ताकि relative image paths सही से लोड हों।

## Folder Structure

```
ravi-mishra-website/
├── index.html          # पूरी वेबसाइट (HTML + CSS + JS एक ही फाइल में)
├── images/             # सभी फोटो
│   ├── ravi-mishra.jpg
│   ├── ravi-mishra-banner.png
│   ├── narendra-modi.jpg
│   ├── mahesh-sharma.jpg
│   └── pankaj-singh.jpg
├── CLAUDE.md            # Claude Code के लिए project context (auto-read होती है)
├── CONTENT.md           # सारा verified source content — WhatsApp चैट से निकाला गया
└── README.md            # यह फाइल
```

## VS Code + Claude Code में काम करना

1. इस पूरे folder को VS Code में खोलें
2. Claude Code extension/CLI इस्तेमाल करें — यह अपने-आप `CLAUDE.md` पढ़ लेगा और project का context समझ जाएगा
3. कोई भी नई content जोड़ने से पहले Claude Code को `CONTENT.md` check करने के लिए कहें ताकि facts सही रहें
4. Design tokens (colors, fonts) `CLAUDE.md` में documented हैं

## Deployment

यह static HTML site है, इसलिए किसी भी static hosting पर डाला जा सकता है:

- **GitHub Pages** — repo बनाकर push करें, Settings → Pages से enable करें
- **Netlify / Vercel** — folder को drag-and-drop करें
- **किसी भी शेयर्ड hosting** — `index.html` और `images/` folder दोनों को साथ upload करें

⚠️ **ज़रूरी:** `index.html` और `images/` folder को हमेशा साथ रखें — अगर अलग किया तो फोटो टूट जाएंगी (broken image icons दिखेंगे)।

## अभी pending items

- [ ] Photo gallery section में real event photos जोड़नी हैं (अभी placeholder icons हैं)
- [ ] Contact form अभी `mailto:` से काम करता है — अगर real backend चाहिए (जैसे Formspree या EmailJS) तो बताएं
- [ ] Contact email address (`ravimishra2121@gmail.com`) confirm करना है — यह अभी अनुमानित है

## Content का स्रोत

सारा content एक WhatsApp ग्रुप ("BJP Ravi Mishra Fans Club") की चैट से निकाला गया और verify किया गया है। विस्तृत सूची और references के लिए `CONTENT.md` देखें।
"# Ravi-mishra-website" 
