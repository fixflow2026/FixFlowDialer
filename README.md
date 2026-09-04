# FixFlow Dialer — Setup Guide (Hinglish)

Ye ek complete Android Studio project hai. Neeche diye steps follow karke aap ise apne phone mein install kar sakte ho.

## Step 1: Android Studio kholna
1. [Android Studio](https://developer.android.com/studio) install karein (agar pehle se nahi hai).
2. Android Studio kholein → **Open** → is `CallHistoryDialer` folder ko select karein.
3. Gradle sync hone dein (pehli baar thoda time lagega, internet chahiye).

## Step 2: App icon add karna (zaroori)
Is project mein app icon (`ic_launcher`) shamil nahi hai. Android Studio mein:
1. `app/res` folder par right-click karein → **New** → **Image Asset**.
2. Koi bhi icon ya text choose karke **Finish** dabayein.
Ye automatically saare zaroori icon files bana dega.

## Step 3: Run karna
1. Apna Android phone USB se connect karein (USB Debugging on karke), ya ek emulator use karein.
2. Upar **Run ▶** button dabayein.
3. App khulte hi ye permission maangega:
   - **Call Log** — recent calls dikhane ke liye
   - **Contacts** — saved naam dikhane ke liye
   Dono ko **Allow** karein.

## Features
- Home screen par saari recent calls list mein dikhengi (naam/number, type — Incoming/Outgoing/Missed, date-time).
- Kisi bhi call par click karne se **Detail screen** khulti hai jismein:
  - Poora number, naam, call type, date/time, duration
  - **Call Karein** button — seedha dial karta hai
  - **WhatsApp par jaayein** button — regular WhatsApp mein us number ka chat kholta hai
  - **WhatsApp Business par jaayein** button — WhatsApp Business app mein us number ka chat kholta hai
  - **Facebook par search karein** button — Facebook app/website mein us number ko search kar deta hai
  - **Instagram par search karein** button — Instagram mein us number ko search kar deta hai

### Facebook / Instagram search — important limitation
Facebook aur Instagram koi public API nahi dete jisse number daal ke automatically pata chale ki account hai ya nahi, aur seedha profile khul jaaye — ye privacy ki wajah se allowed nahi hai kisi bhi app ko. Ye buttons sirf number ko **search box mein daal dete hain**. Agar us number se bana account "phone number se searchable" set hai, to result mein dikhega aur aapko manually tap karke profile kholni hogi. Match na milna bhi possible hai.

## Important note — number format
`WhatsAppLauncher.kt` file mein agar number 10-digit ka hai (bina country code ke), to automatically **India ka country code "91"** add ho jata hai. Agar aapko doosra country code chahiye to `WhatsAppLauncher.kt` mein `defaultCountryCode` value change kar dein.

## Note
Ye app sirf tabhi kaam karega jab phone mein WhatsApp aur/ya WhatsApp Business already installed ho. Agar install nahi hai to app ek chhota message dikhayega.
