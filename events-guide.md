# events.json — कार्यक्रम गाइड / Events Guide

## हिंदी में

### events.json क्या है?

यह फाइल वेबसाइट के कार्यक्रम कैलेंडर को data प्रदान करती है। नया कार्यक्रम जोड़ने के लिए `events` array में एक नई JSON entry जोड़ें।

### एक event का format

```json
{
  "date": "2026-09",
  "type": "conducted",
  "cat": "sangathan",
  "title": {
    "hi": "हिंदी शीर्षक",
    "en": "English Title"
  },
  "place": {
    "hi": "स्थान हिंदी में",
    "en": "Place in English"
  },
  "desc": {
    "hi": "विवरण हिंदी में",
    "en": "Description in English"
  },
  "links": [
    { "type": "facebook", "url": "https://facebook.com/ravimishra2121" }
  ]
}
```

### fields का विवरण

| Field | मान्य values | विवरण |
|---|---|---|
| `date` | `"YYYY-MM"` | वर्ष और महीना (जैसे `"2026-09"`) |
| `type` | `"conducted"` या `"participated"` | `conducted` = आयोजित, `participated` = सहभागिता |
| `cat` | `"sangathan"`, `"seva"`, `"dharmik"`, `"vikas"` | श्रेणी |
| `title.hi` | string | हिंदी शीर्षक |
| `title.en` | string | अंग्रेज़ी शीर्षक |
| `place.hi` | string | स्थान (हिंदी) |
| `place.en` | string | स्थान (अंग्रेज़ी) |
| `desc.hi` | string | विस्तृत विवरण (हिंदी) |
| `desc.en` | string | विस्तृत विवरण (अंग्रेज़ी) |
| `links` | array | संबंधित लिंक; `type` = `"facebook"`, `"instagram"`, `"news"`, `"youtube"` |

### नया event जोड़ने के चरण

1. `events.json` फाइल खोलें।
2. `"events"` array के अंत में (अंतिम `}` के बाद, `]` से पहले) नई entry जोड़ें।
3. `"updated"` field को आज की तारीख़ से बदलें (format: `"YYYY-MM-DD"`).
4. फाइल save करें।
5. वेबसाइट reload करें — कैलेंडर में नया event दिखेगा।

### ध्यान देने योग्य बातें

- `date` field में केवल वर्ष और महीना डालें, दिनांक नहीं (format: `"2026-09"`)।
- `type: "conducted"` = नारंगी रंग (आयोजित कार्यक्रम)।
- `type: "participated"` = हरा-नीला रंग (सहभागिता)।
- `desc` में real quotes हों तो escaped double-quotes `\"` का उपयोग करें।
- JSON valid होना ज़रूरी है — jsonlint.com पर check करें।

---

## In English

### What is events.json?

This file provides data to the website's programme calendar. To add a new event, add a new JSON entry to the `events` array.

### Event Format

```json
{
  "date": "2026-09",
  "type": "conducted",
  "cat": "sangathan",
  "title": { "hi": "Hindi Title", "en": "English Title" },
  "place": { "hi": "Place in Hindi", "en": "Place in English" },
  "desc": { "hi": "Hindi description", "en": "English description" },
  "links": [{ "type": "facebook", "url": "https://facebook.com/ravimishra2121" }]
}
```

### Field Reference

| Field | Valid values | Notes |
|---|---|---|
| `date` | `"YYYY-MM"` | Year and month only, e.g. `"2026-09"` |
| `type` | `"conducted"` or `"participated"` | Conducted = आयोजित; Participated = सहभागिता |
| `cat` | `"sangathan"`, `"seva"`, `"dharmik"`, `"vikas"` | Category |
| `title.hi` / `title.en` | string | Bilingual title |
| `place.hi` / `place.en` | string | Bilingual venue |
| `desc.hi` / `desc.en` | string | Bilingual description |
| `links` | array | Related links. `type` can be `"facebook"`, `"instagram"`, `"news"`, `"youtube"` |

### Steps to add a new event

1. Open `events.json`.
2. Append the new entry inside the `"events"` array (after the last `}`, before the closing `]`).
3. Update the top-level `"updated"` field to today's date (`"YYYY-MM-DD"`).
4. Save the file.
5. Reload the website — the new event will appear in the calendar.

### Notes

- The `date` field takes year-month only, no day.
- Validate your JSON at jsonlint.com before publishing.
- `conducted` events appear in saffron/orange; `participated` events in teal.
- Escape internal double-quotes inside strings: `\"like this\"`.
