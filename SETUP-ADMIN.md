# Portfolio Admin Panel Setup (Decap CMS)

මේකෙන් ඔයාට **code touch නොකර** website content edit කරන්න පුළුවන්.

Admin panel: https://sadeepa-malinga.github.io/portfolio/admin/

---

## 1. Files ටික Repo එකට දාන්න

මේ folder structure එක තියාගන්න:

```
portfolio/
├── index.html              ← updated (JSON එකෙන් load වෙන)
├── content.json            ← ඔයා edit කරන හැම data එකම මෙතන
├── admin/
│   ├── index.html
│   └── config.yml
├── images/                 ← අලුත් photos upload වෙන්නේ මෙතන
└── WhatsApp Image ....jpeg ← ඔයාගේ current photo (තියාගන්න)
```

**කරන්නේ:**
1. GitHub එකට ගිහින් `sadeepa-malinga/portfolio` repo එක open කරන්න
2. මේ files ටික upload / commit කරන්න (`main` branch එකට)

---

## 2. GitHub OAuth App එක හදන්න (Login එකට අනිවාර්යයි)

1. GitHub → **Settings** → **Developer settings** → **OAuth Apps** → **New OAuth App**
2. මේ details ටික දාන්න:

   | Field                    | Value                                              |
   |--------------------------|----------------------------------------------------|
   | Application name         | Sadeepa Portfolio CMS                              |
   | Homepage URL             | https://sadeepa-malinga.github.io/portfolio        |
   | Authorization callback URL | https://decap-cms-oauth.netlify.app/callback     |

3. **Register application** කරන්න
4. Client ID එක copy කරගන්න (දැන් අවශ්‍ය නැහැ – public proxy එක use කරන නිසා)

> Note: අපි public OAuth proxy (`decap-cms-oauth.netlify.app`) use කරනවා. ඒක නිසා Client Secret එක ඕනේ නැහැ.

---

## 3. Admin Panel එකට Login වෙන්න

1. Browser එකෙන් මේ link එකට යන්න:  
   **https://sadeepa-malinga.github.io/portfolio/admin/**

2. **Login with GitHub** button එක click කරන්න
3. GitHub authorization දෙන්න
4. ඊට පස්සේ **Site Content → All Portfolio Content** කියලා එනවා
5. ඕනේ fields edit කරලා **Publish** / **Save** කරන්න

Save කළාම automatically GitHub එකට commit වෙලා site එක update වෙනවා (1-2 minutes ඇතුළත).

---

## 4. Photo change කරන විදිහ

Admin panel එකේ **Profile Photo** field එකෙන් අලුත් image එකක් upload කරන්න.  
ඒක `images/` folder එකට යනවා.  
`content.json` එකේ path එකත් automatically update වෙනවා.

---

## 5. Troubleshooting

| Problem | Solution |
|---------|----------|
| Login page එකේ error එනවා | OAuth App callback URL එක හරියට තියෙනවද බලන්න |
| Changes save වෙලා site එකේ පේන්නේ නැහැ | 1-2 minutes ඉන්න / hard refresh (Ctrl+Shift+R) |
| content.json load වෙන්නේ නැහැ | Browser console බලන්න. File path හරිද බලන්න |
| Image upload fail | `images` folder එක repo එකේ තියෙනවද බලන්න |

---

## Security Note

Admin panel එකට access තියෙන්නේ **ඔයාගේ GitHub account** එකට write permission තියෙන අයට විතරයි.  
අනිත් අයට login වෙන්න බැහැ.
