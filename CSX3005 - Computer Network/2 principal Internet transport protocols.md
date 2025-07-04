![[Pasted image 20250630102512.png]]
ဟုတ်ကဲ့ပါ။ ဒီ slide မှာ ဖော်ပြထားတဲ့ အင်တာနက်ရဲ့ အဓိက Transport Protocol နှစ်မျိုးဖြစ်တဲ့ TCP နဲ့ UDP အကြောင်းကို ကွန်ပျူတာကွန်ရက် ရှုထောင့်ကနေ အသေးစိတ်ရှင်းပြပြီး၊ ဆက်စပ်ပြီး သိထားသင့်တဲ့ အရေးကြီးတဲ့ အချက်အလက်တွေကိုပါ မြန်မာဘာသာဖြင့် ရှင်းလင်းတင်ပြပေးပါ့မယ်။

### **Slide အကျဉ်းချုပ် ရှင်းလင်းချက်**

ဒီ slide က အင်တာနက်မှာ အသုံးအများဆုံး Transport Layer protocol နှစ်ခုဖြစ်တဲ့ **TCP (Transmission Control Protocol)** နဲ့ **UDP (User Datagram Protocol)** တို့ရဲ့ အဓိက లక్షణတွေနဲ့ ကွာခြားချက်တွေကို မီးမောင်းထိုးပြထားပါတယ်။

#### **1. TCP: Transmission Control Protocol**

TCP ဟာ "စိတ်ချရမှု" ကို အဓိကထားတဲ့ protocol တစ်ခုဖြစ်ပါတယ်။ သူ့ရဲ့ ဝန်ဆောင်မှုတွေကတော့:

*   **Reliable, in-order delivery (စိတ်ချရပြီး အစဉ်လိုက်မှန်ကန်စွာ ပို့ဆောင်ခြင်း):**
    *   **Reliable:** ပေးပို့လိုက်တဲ့ data segment တိုင်း လက်ခံသူဆီကို ရောက်၊ မရောက် အတည်ပြုချက် (Acknowledgement - ACK) ပြန်တောင်းပါတယ်။ အကယ်၍ data ပျောက်ဆုံးသွားရင် ဒါမှမဟုတ် error ပါသွားရင် ပေးပို့သူ (sender) က အဲဒီ data ကို အလိုအလျောက် ပြန်ပို့ပေးပါတယ်။
    *   **In-order:** Data segment တွေကို နံပါတ်စဉ် (sequence number) တပ်ပြီး ပို့လွှတ်ပါတယ်။ လက်ခံသူ (receiver) ဘက်မှာ အကယ်၍ segment တွေက အစဉ်လိုက်မဟုတ်ဘဲ ရောက်လာရင်တောင် နံပါတ်စဉ်အတိုင်း ပြန်လည်စီစဉ်ပေးပြီးမှ Application Layer ကို ပို့ပေးပါတယ်။

*   **Congestion Control (ကွန်ရက်ကျပ်တည်းမှု ထိန်းချုပ်ခြင်း):**
    *   ကွန်ရက်လမ်းကြောင်းပေါ်မှာ data တွေ အရမ်းများပြီး ပိတ်ဆို့ကျပ်တည်းလာတဲ့အခါ (network congestion)၊ TCP က အခြေအနေကို သိရှိပြီး data ပို့လွှတ်တဲ့နှုန်းကို အလိုအလျောက် လျှော့ချပေးပါတယ်။ ဒါမှ ကွန်ရက်တစ်ခုလုံးရဲ့ စွမ်းဆောင်ရည် မကျဆင်းအောင် ကာကွယ်ပေးပါတယ်။

*   **Flow Control (အသွားအနှုန်း ထိန်းချုပ်ခြင်း):**
    *   ပေးပို့သူ (sender) က data ကို အရှိန်နဲ့ ပို့နေပြီး လက်ခံသူ (receiver) က အဲဒီနှုန်းအတိုင်း မဖတ်နိုင်၊ မသိမ်းနိုင် ဖြစ်နေရင်၊ လက်ခံသူက ပေးပို့သူကို "ခဏစောင့်ပါ" သို့မဟုတ် "နှုန်းလျှော့ပါ" လို့ အချက်ပြနိုင်ပါတယ်။ ဒါမှ လက်ခံသူရဲ့ buffer မပြည့်လျှံသွားအောင် ကာကွယ်ပေးပါတယ်။

*   **Connection Setup (ဆက်သွယ်မှု ထူထောင်ခြင်း):**
    *   Data မပို့ခင်မှာ sender နဲ့ receiver ကြားမှာ **Three-Way Handshake** လို့ခေါ်တဲ့ လုပ်ငန်းစဉ်သုံးပြီး ဆက်သွယ်မှုလမ်းကြောင်း (connection) တစ်ခုကို အရင်ဆုံး တည်ဆောက်ပါတယ်။ ဒီလိုလုပ်ခြင်းအားဖြင့် နှစ်ဖက်စလုံးက data လက်ခံဖို့/ပို့ဖို့ အသင့်ဖြစ်ကြောင်း သေချာစေပါတယ်။

#### **2. UDP: User Datagram Protocol**

UDP ကတော့ "မြန်ဆန်မှု" နဲ့ "ရိုးရှင်းမှု" ကို အဓိကထားတဲ့ protocol ဖြစ်ပါတယ်။

*   **Unreliable, unordered delivery (စိတ်မချရ၊ အစဉ်လိုက်မဟုတ်သော ပို့ဆောင်မှု):**
    *   UDP က data packet (datagram) တွေကို ပို့ပြီးရင်ပြီးရော ပုံစံ (fire-and-forget) နဲ့ ပို့ပါတယ်။ ရောက်မရောက် အတည်ပြုချက်ပြန်မတောင်းပါဘူး။ ပျောက်သွားလည်း ပြန်မပို့ပါဘူး။ ရောက်လာတဲ့ packet တွေကလည်း အစဉ်လိုက်မှန်ချင်မှ မှန်ပါမယ်။

*   **No-frills extension of "best-effort" IP (အပိုအလိုမရှိသော "အတတ်နိုင်ဆုံး" IP ၏ တိုးချဲ့မှု):**
    *   "No-frills" ဆိုတာ အပိုဝန်ဆောင်မှုတွေ ဘာမှမပါဘူးလို့ ဆိုလိုတာပါ။ Network Layer က IP protocol ဟာ "best-effort" (အတတ်နိုင်ဆုံးကြိုးစားပြီးပို့ပေးမယ်၊ ဒါပေမဲ့ အာမမခံ) ဝန်ဆောင်မှုပေးပါတယ်။ UDP က အဲဒီ IP ဝန်ဆောင်မှုအပေါ်မှာ **Port Number** တစ်ခုပဲ ပေါင်းထည့်ပေးလိုက်တာပါ။ ဒါကြောင့် process-to-process communication ဖြစ်သွားတာကလွဲရင် ကျန်တာတွေက IP နဲ့ အတူတူနီးပါးပါပဲ။

#### **3. Transport Layer မှ မပေးနိုင်သော ဝန်ဆောင်မှုများ (Services *not* available)**

TCP ဖြစ်စေ UDP ဖြစ်စေ၊ ဒီ protocol တွေက အောက်ပါအချက်တွေကို အာမမခံနိုင်ပါဘူး။

*   **Delay guarantees (အချိန်ကြန့်ကြာမှု အာမခံချက်):** Data packet တစ်ခုဟာ အချိန်အတိအကျ (ဥပမာ 100 milliseconds) အတွင်း ရောက်ရှိမယ်လို့ အာမမခံနိုင်ပါဘူး။ ကွန်ရက်အခြေအနေပေါ်မူတည်ပြီး အချိန်က ပြောင်းလဲနိုင်ပါတယ်။
*   **Bandwidth guarantees (ဒေတာပို့လွှတ်နှုန်း အာမခံချက်):** အနည်းဆုံး data ပို့လွှတ်နှုန်း (ဥပမာ 1 Mbps) ကို အမြဲတမ်းရရှိမယ်လို့ အာမမခံနိုင်ပါဘူး။

---

### **ထပ်မံသိရှိထားသင့်သော အရေးကြီးသည့် အချက်များ (Must-Know Knowledge)**

#### **ဘယ်အချိန်မှာ TCP သုံးမလဲ? ဘယ်အချိန်မှာ UDP သုံးမလဲ?**

Application ရဲ့ လိုအပ်ချက်ပေါ်မူတည်ပြီး သင့်တော်တဲ့ protocol ကို ရွေးချယ်ရပါတယ်။

*   **TCP ကို သုံးသင့်သော Application များ:**
    *   **လိုအပ်ချက်:** Data တစ်စက်မှ မပျောက်ဆုံးစေချင်၊ အစဉ်လိုက်မှန်ကန်ဖို့ အလွန်အရေးကြီးတဲ့ Application များ။
    *   **ဥပမာများ:**
        *   **Web Browsing (HTTP/HTTPS):** ဝဘ်စာမျက်နှာရဲ့ စာသားတွေ၊ ပုံတွေ အပြည့်အစုံမှန်ကန်စွာ ပေါ်ဖို့လိုပါတယ်။
        *   **File Transfer (FTP, SFTP):** ဒေါင်းလုဒ်ဆွဲတဲ့ ဖိုင်က နည်းနည်းလေးမှ ပျက်စီးလို့မရပါဘူး။
        *   **Email (SMTP, IMAP):** ပို့လိုက်တဲ့ အီးမေးလ်စာသားတွေ အပြည့်အစုံ ရောက်ရှိဖို့ လိုပါတယ်။

*   **UDP ကို သုံးသင့်သော Application များ:**
    *   **လိုအပ်ချက်:** မြန်နှုန်း (Speed) က အဓိက၊ data အနည်းငယ် ပျောက်ဆုံးသွားလည်း (loss-tolerant) ပြဿနာမရှိတဲ့ Application များ။
    *   **ဥပမာများ:**
        *   **Video Streaming (ဥပမာ- YouTube, Netflix):** ဗီဒီယို frame တစ်ခုလောက် ပျောက်သွားလည်း နောက် frame တွေ ဆက်ကြည့်နေလို့ရပါတယ်။ ဗီဒီယိုတစ်ခုလုံး ရပ်တန့်ပြီး ပျောက်သွားတဲ့ frame ကို ပြန်စောင့်နေတာထက်စာရင် ပိုကောင်းပါတယ်။
        *   **Online Gaming:** ဂိမ်းထဲက player ရဲ့ တည်နေရာ update ဟာ အမြန်ဆုံးရောက်ဖို့လိုပါတယ်။ အချက်အလက်အဟောင်းတစ်ခု ပျောက်သွားလည်း နောက်ထပ် အချက်အလက်အသစ်က ချက်ချင်းရောက်လာမှာမို့ မြန်နှုန်းက ပိုအရေးကြီးပါတယ်။
        *   **Voice over IP (VoIP) (ဥပမာ- Skype, Viber calls):** စကားပြောဆိုရာမှာ အသံနည်းနည်းပြတ်သွားတာက လက်ခံနိုင်ပေမယ့်၊ စကားပြောတာက အချိန်အကြာကြီး ရပ်တန့်နေတာကို လက်မခံနိုင်ပါဘူး။
        *   **DNS (Domain Name System):** web address ကို IP address ပြောင်းလဲမေးမြန်းတဲ့အခါ မြန်မြန်အဖြေရဖို့လိုပါတယ်။ မရရင် နောက်တစ်ခါပြန်မေးလိုက်ရုံပါပဲ။

### **အနှစ်ချုပ်**

*   **TCP** = **ယုံကြည်စိတ်ချရမှု (Reliable)**၊ **စနစ်ကျမှု (Ordered)**၊ ဒါပေမဲ့ **အနည်းငယ်ပိုနှေးပြီး အလုပ်ရှုပ်တယ်**။
*   **UDP** = **အလွန်မြန်ဆန်မှု (Fast)**၊ **ရိုးရှင်းမှု (Simple)**၊ ဒါပေမဲ့ **မသေချာမရေရာဘူး (Unreliable)**။

Application တစ်ခုကို တီထွင်တဲ့အခါ၊ အဲဒီ application ရဲ့ data ဆက်သွယ်ရေးလိုအပ်ချက်ဟာ "စိတ်ချရမှု" လား "မြန်ဆန်မှု" လားဆိုတာကို အရင်ဆုံးသုံးသပ်ပြီး TCP သို့မဟုတ် UDP ကို သင့်တော်သလို ရွေးချယ်အသုံးပြုရပါတယ်။