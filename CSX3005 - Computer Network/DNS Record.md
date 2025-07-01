![[Screenshot 2025-06-23 at 10.50.36 AM.png]]
ဒီ slide မှာ ဖော်ပြထားတဲ့ **DNS Records** အကြောင်းကို အသေးစိတ်ရှင်းပြပေးပါမယ်။

---

### ဒီ Slide ရဲ့ အဓိက အကြောင်းအရာ

ဒီ slide က DNS ဆိုတဲ့ ဖြန့်ကျက်ထားတဲ့ database ကြီးထဲမှာ အချက်အလက်တွေကို ဘယ်လိုပုံစံနဲ့ သိမ်းဆည်းသလဲဆိုတာကို ရှင်းပြထားပါတယ်။ ဒီအချက်အလက်တွေကို **Resource Records (RR)** လို့ခေါ်ပါတယ်။ Record တစ်ခုစီမှာ သူ့ရဲ့ ရည်ရွယ်ချက်နဲ့ ကိုက်ညီတဲ့ အမျိုးအစား (type) တွေ ရှိပါတယ်။

---

### Resource Record (RR) Format

အနီရောင်ဘောင်ခတ်ထားတဲ့ အကွက်ထဲမှာ ပြထားတဲ့အတိုင်း DNS record တိုင်းမှာ အောက်ပါ အချက် (၄) ချက် ပါဝင်ပါတယ်:

**`RR format: (name, value, type, ttl)`**

1.  **Name:** Record နဲ့ သက်ဆိုင်တဲ့ Domain Name ဒါမှမဟုတ် Hostname (ဥပမာ `www.google.com`)။
2.  **Value:** Name နဲ့ ဆက်စပ်နေတဲ့ အချက်အလက်။ ဒါက IP address လည်းဖြစ်နိုင်သလို、အခြား domain name လည်း ဖြစ်နိုင်ပါတယ်။
3.  **Type:** ဒီ Record က ဘာအတွက်သုံးတာလဲဆိုတာကို သတ်မှတ်ပေးတဲ့ အမျိုးအစား (ဥပမာ A, CNAME, MX)။
4.  **TTL (Time To Live):** ဒီ Record ကို တခြား DNS Server တွေက သူတို့ရဲ့ cache (ကြားခံမှတ်ဉာဏ်) မှာ ဘယ်လောက်ကြာကြာ မှတ်ထားခွင့်ရှိသလဲဆိုတဲ့ အချိန် (စက္ကန့်နဲ့ပြပါတယ်)။ TTL ပြည့်သွားရင် အချက်အလက်အသစ်ကို ပြန်လာမေးရပါတယ်။

---

### အသုံးများသော DNS Record အမျိုးအစားများ (Types)

Slide မှာ အသုံးအများဆုံး Record အမျိုးအစား (၄) မျိုးကို ရှင်းပြထားပါတယ်:

#### 1. `type=A` (A Record)

*   **A** ဆိုတာ **Address** ကို ဆိုလိုပါတယ်။ ဒါက အခြေခံအကျဆုံးနဲ့ အသုံးအများဆုံး Record ပါ။
*   **Name:** Hostname တစ်ခုဖြစ်ပါတယ် (ဥပမာ `www.google.com`)။
*   **Value:** အဲ့ဒီ Hostname ရဲ့ **IPv4 Address** ဖြစ်ပါတယ် (ဥပမာ `172.217.167.78`)။
*   **အနှစ်ချုပ်:** **Hostname တစ်ခုကို IP Address တစ်ခုနဲ့ တွဲချိတ်ပေးပါတယ်**။

#### 2. `type=NS` (NS Record)

*   **NS** ဆိုတာ **Name Server** ကို ဆိုလိုပါတယ်။
*   **Name:** Domain တစ်ခုဖြစ်ပါတယ် (ဥပမာ `google.com`)။
*   **Value:** အဲ့ဒီ Domain အတွက် တာဝန်ရှိတဲ့ **Authoritative Name Server ရဲ့ Hostname** ဖြစ်ပါတယ် (ဥပမာ `ns1.google.com`)။
*   **အနှစ်ချုပ်:** **"ဒီ domain (`google.com`) ရဲ့ အချက်အလက်အမှန်တွေကို ဘယ် server (`ns1.google.com`) မှာ သွားမေးရမလဲ" ဆိုတာကို လမ်းညွှန်ပေးပါတယ်**။

#### 3. `type=CNAME` (CNAME Record)

*   **CNAME** ဆိုတာ **Canonical Name** (နာမည်ရင်း/နာမည်မှန်) ကို ဆိုလိုပါတယ်။ ဒါကို "နာမည်ပြောင်" (alias) record လို့လည်း ခေါ်ကြပါတယ်။
*   **Name:** နာမည်ပြောင် (alias) တစ်ခုဖြစ်ပါတယ် (ဥပမာ `www.ibm.com`)။
*   **Value:** အဲ့ဒီနာမည်ပြောင်က တကယ်တမ်းညွှန်းဆိုတဲ့ **နာမည်ရင်း (canonical name)** ဖြစ်ပါတယ် (ဥပမာ `servereast.backup2.ibm.com`)။
*   **ဥပမာ:** User က `www.ibm.com` ကို ဝင်ကြည့်တဲ့အခါ DNS က "အိုး... `www.ibm.com` ဆိုတာ တကယ်တော့ `servereast.backup2.ibm.com` ကိုပြောတာပဲ" လို့သိပြီး `servereast.backup2.ibm.com` ရဲ့ IP Address ကို ဆက်ရှာပေးပါတယ်။
*   **အနှစ်ချုပ်:** **Domain name တစ်ခုကို နောက် domain name တစ်ခုဆီသို့ ပြန်လည်ညွှန်းဆိုပေးပါတယ်**။ IP address ကို တိုက်ရိုက်မညွှန်းပါဘူး။

#### 4. `type=MX` (MX Record)

*   **MX** ဆိုတာ **Mail Exchanger** ကို ဆိုလိုပါတယ်။ Email ပို့တဲ့နေရာမှာ အသုံးဝင်ပါတယ်။
*   **Name:** Email လက်ခံမယ့် Domain ဖြစ်ပါတယ် (ဥပမာ `gmail.com`)။
*   **Value:** အဲ့ဒီ Domain အတွက် Email တွေကို လက်ခံဆောင်ရွက်ပေးမယ့် **Mail Server (SMTP server) ရဲ့ Hostname** ဖြစ်ပါတယ် (ဥပမာ `aspmx.l.google.com`)။
*   **အနှစ်ချုပ်:** **"ဒီ domain (`gmail.com`) ကို email ပို့ချင်ရင် ဘယ် mail server ဆီကို သွားပို့ရမလဲ" ဆိုတာကို လမ်းညွှန်ပေးပါတယ်**။

---

### အဓိကအချက်များ (Key Points)

1.  **Resource Records (RR) များဖြင့် ဖွဲ့စည်းခြင်း:** DNS database သည် RR ဟုခေါ်သော records များဖြင့် ဖွဲ့စည်းထားပြီး record တိုင်းတွင် `(name, value, type, ttl)` ပါဝင်သည်။
2.  **A Record သည် IP Address ကို ညွှန်းဆိုခြင်း:** `A` record သည် hostname ကို တိုက်ရိုက် IP address နှင့် ချိတ်ဆက်ပေးသည်။
3.  **NS Record သည် Name Server ကို ညွှန်းဆိုခြင်း:** `NS` record သည် domain တစ်ခု၏ အချက်အလက်များအတွက် တာဝန်ရှိသော server ကို လမ်းညွှန်ပေးသည်။
4.  **CNAME Record သည် နာမည်ပြောင်အဖြစ် အလုပ်လုပ်ခြင်း:** `CNAME` record သည် domain name တစ်ခုကို အခြား domain name တစ်ခုဆီသို့ ပြန်လည်ညွှန်းဆိုပေးသည်။
5.  **MX Record သည် Mail Server ကို ညွှန်းဆိုခြင်း:** `MX` record သည် email များ လက်ခံဆောင်ရွက်ပေးမည့် mail server ကို သတ်မှတ်ပေးသည်။