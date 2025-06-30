![[87652083.png]]

### ဒီပုံ (Slide) ရဲ့ အဓိက အကြောင်းအရာ

ဒီ slide က **DNS (Domain Name System)** ရဲ့ အလုပ်လုပ်ပုံ အခြေခံကို ရှင်းပြထားတာပါ။ DNS ဆိုတာ အင်တာနက်ရဲ့ "ဖုန်းစာအုပ်ကြီး" နဲ့တူပါတယ်။ ကျွန်တော်တို့က `www.amazon.com` လို လူနားလည်တဲ့ နာမည်ကိုရိုက်ထည့်လိုက်ရင်၊ DNS က အဲ့ဒီနာမည်နဲ့ သက်ဆိုင်တဲ့ IP Address (ဥပမာ `192.0.2.44`) ကို ရှာပေးပါတယ်။

Slide ရဲ့ ခေါင်းစဉ်မှာပါတဲ့ အဓိပ္ပာယ်နှစ်ခုကတော့:
1.  **Distributed (ဖြန့်ကျက်ထားသော):** DNS အချက်အလက်တွေအားလုံးကို Server တစ်လုံးတည်းမှာ သိမ်းထားတာမဟုတ်ဘဲ、ကမ္ဘာတစ်ဝှမ်းက Server ပေါင်းများစွာမှာ ဖြန့်ကျက်ပြီး သိမ်းဆည်းထားပါတယ်။ ဒါကြောင့် Server တစ်ခုပျက်သွားရင်တောင် အင်တာနက်တစ်ခုလုံး ရပ်မသွားပါဘူး။
2.  **Hierarchical (အဆင့်ဆင့် ဖွဲ့စည်းပုံ):** DNS ဟာ သစ်ပင်ပုံစံလို အဆင့်ဆင့် ဖွဲ့စည်းတည်ဆောက်ထားပါတယ်။ အပေါ်ဆုံးအဆင့်ကနေ အောက်ခြေအဆင့်ထိ အဆင့်ဆင့် မေးမြန်းပြီး အဖြေကို ရှာရပါတယ်။

---

### DNS ရဲ့ အဆင့်ဆင့် ဖွဲ့စည်းပုံ (Hierarchical Structure)

ပုံထဲမှာ ပြထားတဲ့ သစ်ပင်ပုံစံက အဆင့် (၃) ဆင့်ကို ဖော်ပြထားပါတယ်:

#### ၁။ Root DNS Servers (အမြစ် DNS Server များ)
*   ဒါက DNS ရဲ့ အမြင့်ဆုံးအဆင့်၊ အမြစ် (Root) ပါ။
*   သူတို့က domain name တွေရဲ့ IP address အတိအကျကို မသိပါဘူး။
*   ဒါပေမယ့် သူတို့က **Top Level Domain (TLD) Server** တွေ (ဥပမာ `.com` server, `.org` server) ဘယ်မှာရှိလဲဆိုတဲ့ လိပ်စာတွေကို သိမ်းထားပါတယ်။

#### ၂။ Top-Level Domain (TLD) DNS Servers
*   ဒါက ဒုတိယအဆင့်ပါ။ Domain name တွေရဲ့ နောက်ဆုံးအပိုင်း (ဥပမာ `.com`, `.org`, `.edu`, `.net`) တွေကို တာဝန်ယူပါတယ်။
*   ဥပမာ၊ `.com` TLD server က `amazon.com`, `yahoo.com` လို `.com` နဲ့ဆုံးတဲ့ domain တွေအားလုံးရဲ့ **Authoritative Server** တွေ ဘယ်မှာရှိလဲဆိုတာကို သိပါတယ်။ သူကိုယ်တိုင် `www.amazon.com` ရဲ့ IP ကို မသိသေးပါဘူး။

#### ၃။ Authoritative DNS Servers
*   ဒါက နောက်ဆုံးနဲ့ အရေးအကြီးဆုံးအဆင့်ပါ။
*   ဒီ Server တွေမှာ သက်ဆိုင်ရာ domain name တစ်ခုရဲ့ IP address အစစ်အမှန်ကို သိမ်းဆည်းထားပါတယ်။
*   ဥပမာ၊ `amazon.com` ရဲ့ Authoritative DNS Server မှာ `www.amazon.com` ရဲ့ IP က ဘာလဲ၊ `aws.amazon.com` ရဲ့ IP က ဘာလဲဆိုတဲ့ အချက်အလက် အတိအကျ ရှိပါတယ်။ အဖြေမှန်ကို ပေးနိုင်တဲ့ နောက်ဆုံးပိုင်ရှင် server ဖြစ်ပါတယ်။

---

### လက်တွေ့ ဥပမာ - `www.amazon.com` ရဲ့ IP ကို ဘယ်လိုရှာသလဲ

Slide ရဲ့ အောက်ခြေမှာ ဖော်ပြထားတဲ့အတိုင်း၊ သင် (Client) က `www.amazon.com` ကို ဝင်ကြည့်ချင်တဲ့အခါ အောက်ပါအဆင့်တွေအတိုင်း အလုပ်လုပ်ပါတယ် (ဒါက ရိုးရှင်းအောင်ရှင်းပြထားတဲ့ ပုံစံပါ)။

*   **အဆင့် ၁: `client queries root server to find .com DNS server`**
    *   ပထမဆုံး၊ သင့်ကွန်ပျူတာက Root Server ကို သွားမေးပါတယ်: "**`.com` TLD Server ရဲ့ လိပ်စာ ဘယ်မှာလဲ?**"
    *   Root Server က `.com` TLD Server ရဲ့ IP address ကို ပြန်ပေးလိုက်ပါတယ်။

*   **အဆင့် ၂: `client queries .com DNS server to get amazon.com DNS server`**
    *   အခု `.com` TLD Server ရဲ့ လိပ်စာကို သိပြီဖြစ်လို့၊ အဲ့ဒီ Server ကို သွားမေးပါတယ်: "**`amazon.com` ရဲ့ Authoritative Server လိပ်စာ ဘယ်မှာလဲ?**"
    *   `.com` TLD Server က `amazon.com` ရဲ့ Authoritative Server ရဲ့ IP address ကို ပြန်ပေးလိုက်ပါတယ်။

*   **အဆင့် ၃: `client queries amazon.com DNS server to get IP address for www.amazon.com`**
    *   နောက်ဆုံးမှာတော့ `amazon.com` ရဲ့ Authoritative Server ဆီကို ရောက်သွားပြီး တိုက်ရိုက်မေးပါတယ်: "**`www.amazon.com` ရဲ့ IP address အတိအကျက ဘာလဲ?**"
    *   အဲ့ဒီအခါမှ Authoritative Server က တကယ့် IP Address အမှန်ကို ပြန်ပေးပြီး၊ သင့် browser က အဲ့ဒီ IP ကို သုံးပြီး Amazon website ကို သွားရောက် ဆက်သွယ်ပါတယ်။

---

### အဓိကအချက်များ (Key Points)

1.  **DNS သည် အဆင့်ဆင့် ဖွဲ့စည်းထားသည် (Hierarchical):** အဖြေတစ်ခုရဖို့ အမြင့်ဆုံးအဆင့် (Root) ကနေ အောက်ခြေအဆင့် (Authoritative) အထိ အဆင့်ဆင့် မေးမြန်းရပါတယ်။
2.  **DNS သည် ဖြန့်ကျက်ထားသည် (Distributed):** အချက်အလက်အားလုံးကို Server တစ်လုံးတည်းမှာ မထားဘဲ ကမ္ဘာအနှံ့ရှိ Server များတွင် ခွဲဝေသိမ်းဆည်းထားသည်။
3.  **အဆင့်ဆင့် မေးမြန်းမှု (Iterative Query):** IP address တစ်ခုကို ရှာဖွေရာမှာ Server တစ်ခုက နောက် Server တစ်ခုကို လက်ညှိုးထိုး လမ်းညွှန်ပေးတဲ့ ပုံစံနဲ့ အဆင့်ဆင့် ရှာဖွေသွားရပါတယ်။
4.  **Server အမျိုးအစား (၃) မျိုး:** DNS မှာ အဓိကအားဖြင့် **Root**, **Top-Level Domain (TLD)**, နှင့် **Authoritative** ဆိုပြီး Server အဆင့် (၃) ဆင့် ရှိပါတယ်။