![[Pasted image 20250630102832.png]]

ဟုတ်ကဲ့ပါ။ ဒီ slide မှာ ဖော်ပြထားတဲ့ "Multiplexing/Demultiplexing" ဆိုတဲ့ အလွန်အရေးကြီးတဲ့ Transport Layer ရဲ့ သဘောတရားကို ကွန်ပျူတာကွန်ရက် ရှုထောင့်ကနေ အသေးစိတ်ရှင်းပြပြီး၊ ဆက်စပ်ပြီး သိထားသင့်တဲ့ အချက်အလက်တွေကိုပါ မြန်မာဘာသာဖြင့် ရှင်းလင်းတင်ပြပေးပါ့မယ်။

### **Slide အကျဉ်းချုပ် ရှင်းလင်းချက်**

ဒီ slide က ကွန်ပျူတာတစ်လုံးတည်းမှာ application တွေအများကြီး (ဥပမာ- browser, game, chat app) တစ်ပြိုင်နက်တည်း အင်တာနက်ကို ဘယ်လိုသုံးနေကြသလဲ၊ ပြီးတော့ အင်တာနက်ကနေ ပြန်ရောက်လာတဲ့ data တွေက သက်ဆိုင်ရာ application ဆီကို မှန်မှန်ကန်ကန် ဘယ်လိုပြန်ရောက်သွားသလဲ ဆိုတာကို ရှင်းပြထားတာ ဖြစ်ပါတယ်။ ဒီလုပ်ငန်းစဉ်ကို **Multiplexing** နဲ့ **Demultiplexing** လို့ခေါ်ပါတယ်။

**ရိုးရှင်းတဲ့ ဥပမာတစ်ခုနဲ့ အရင်ရှင်းပြပါမယ်။**

*   **Multiplexing (စုစည်းပေါင်းထည့်ခြင်း):** တိုက်ခန်းအဆောက်အအုံတစ်ခုမှာ နေတဲ့လူတွေ (Application တွေ) က သူတို့ရဲ့စာတွေကို (Data တွေကို) စာအိတ်ထဲထည့်ပြီး အဆောက်အအုံရဲ့ အောက်ထပ်က စာပုံးကြီးတစ်ခုထဲကို (Transport Layer) အကုန်စုထည့်လိုက်တာနဲ့ တူပါတယ်။ စာပို့သမားက အဲဒီစာပုံးကြီးထဲက စာတွေအကုန်လုံးကို တစ်ခါတည်း ယူသွားပါတယ်။
*   **Demultiplexing (ပြန်လည်ခွဲဝေခြင်း):** စာပို့သမားက တခြားနေရာကနေ စာတွေယူလာပြီး အဲဒီတိုက်ခန်းအဆောက်အအုံကို ရောက်တဲ့အခါ၊ စာအိတ်ပေါ်က တိုက်ခန်းနံပါတ် (Port Number) ကိုကြည့်ပြီး သက်ဆိုင်ရာလူရဲ့ တိုက်ခန်းရှေ့က စာပုံးလေးထဲကို (Socket) မှန်မှန်ကန်ကန် ထည့်ပေးတာနဲ့ တူပါတယ်။

---

### **Slide ရှိ ပုံများအလိုက် အသေးစိတ်ရှင်းလင်းချက်**

#### **၁။ အပေါ်ဆုံး ပုံ (သဘောတရား ရှင်းလင်းချက်)**

*   **Multiplexing as sender (ပေးပို့သူအဖြစ် စုစည်းခြင်း):**
    *   ဘယ်ဘက်က host (ကွန်ပျူတာ) မှာ Process P1 နဲ့ P2 ဆိုပြီး application နှစ်ခု run နေပါတယ်။
    *   Application တစ်ခုချင်းစီက သူတို့ရဲ့ data တွေကို သက်ဆိုင်ရာ **socket** (အဝါရောင်လေးထောင့်ကွက်) ကနေတဆင့် ပေးပို့ပါတယ်။ Socket ဆိုတာ application ရဲ့ ကွန်ရက်ဆက်သွယ်ရေး တံခါးပေါက်တစ်ခုပါ။
    *   Transport Layer က အဲဒီ socket တွေဆီက data တွေကို လက်ခံပြီး၊ data တစ်ခုချင်းစီရဲ့ ရှေ့မှာ **Transport Header** (ခေါင်းစဉ်အချက်အလက်) ကို ထည့်ပေးလိုက်ပါတယ်။ ဒီ header ထဲမှာ ဘယ်သူပို့တယ်၊ ဘယ်သူ့ဆီပို့တယ်ဆိုတဲ့ အချက်အလက် (အထူးသဖြင့် Port နံပါတ်တွေ) ပါဝင်ပါတယ်။
    *   ပြီးရင် အဲဒီ data တွေကို Network Layer ကို ဆက်ပို့ပါတယ်။

*   **Demultiplexing as receiver (လက်ခံသူအဖြစ် ပြန်ခွဲခြင်း):**
    *   ညာဘက်က host ဆီကို data ရောက်လာတဲ့အခါ၊ Transport Layer က ရောက်လာတဲ့ segment (data အပိုင်းအစ) ရဲ့ **header** ကို စစ်ဆေးပါတယ်။
    *   Header ထဲမှာပါတဲ့ အချက်အလက် (Destination Port Number) ကို ကြည့်ပြီး၊ ဒီ data ဟာ ဘယ် application process (ဥပမာ- P4) အတွက်ဖြစ်တယ်ဆိုတာ သိရှိပါတယ်။
    *   ပြီးရင် အဲဒီ data ကို သက်ဆိုင်ရာ Process P4 ရဲ့ socket ဆီကို မှန်ကန်စွာ ပို့ဆောင်ပေးလိုက်ပါတယ်။

#### **၂။ အလယ်ပုံ (HTTP ဥပမာ)**

ဒီပုံက Client (သုံးစွဲသူ) က Web Server ကို HTTP request ပို့တဲ့ လုပ်ငန်းစဉ်ကို ပြထားတာပါ။

1.  **Client ဘက်မှာ:** Client ကွန်ပျူတာမှာ Skype, Netflix, Firefox ဆိုပြီး application တွေအများကြီး run နေပါတယ်။ Firefox browser ကနေ web server ကို HTTP message တစ်ခုပို့ပါမယ်။
2.  Application Layer မှာ `HTTP msg` ရှိပါတယ်။
3.  Transport Layer က အဲဒီ message ရှေ့မှာ Transport Header (`H_t`) ကို ထပ်ပေါင်းထည့်လိုက်ပါတယ်။ `H_t` ထဲမှာ **Source Port** (Firefox ကသုံးတဲ့ port) နဲ့ **Destination Port** (HTTP Server ရဲ့ port 80) ပါပါမယ်။
4.  Network Layer ကလည်း သူ့ရဲ့ Network Header (`H_n`) ကို ထပ်ပေါင်းပါတယ်။ `H_n` ထဲမှာ Source IP နဲ့ Destination IP ပါပါမယ်။
5.  `H_n H_t HTTP msg` ဆိုတဲ့ packet အပြည့်အစုံကို ကွန်ရက်ပေါ်ကနေတဆင့် Server ဆီ ပို့လွှတ်ပါတယ်။

#### **၃။ အောက်ဆုံးပုံ (အဓိကမေးခွန်း)**

**မေးခွန်း:** Server ကနေ data ပြန်ရောက်လာတဲ့အခါ၊ Client ရဲ့ Transport Layer က ဒီ data ကို Netflix အတွက်လည်းမဟုတ်၊ Skype အတွက်လည်းမဟုတ်ဘဲ၊ **Firefox browser အတွက်ဖြစ်မှန်း ဘယ်လိုသိသလဲ?**

**အဖြေ:** **Port Number** ကြောင့်ပါ။

1.  Client (Firefox) က server ဆီကို request စပို့တုန်းက၊ Transport Header ထဲမှာ **Source Port** နံပါတ်တစ်ခုကို ထည့်ပေးလိုက်ပါတယ်။ ဥပမာ၊ Port `51000` ဆိုပါစို့။ (ဒါကို ephemeral port လို့ခေါ်ပြီး OS ကနေ ကျပန်းရွေးပေးလိုက်တာပါ)။ Destination Port ကတော့ Server ရဲ့ HTTP port `80` ဖြစ်ပါမယ်။
2.  Server က အဲဒီ request ကို လက်ခံရရှိပြီး အဖြေပြန်ပို့တဲ့အခါ၊ သူက header တွေကို ပြောင်းပြန်လှန်ပြီး ပြန်ပို့ပါတယ်။
    *   Server ရဲ့ Source Port က `80` ဖြစ်သွားမယ်။
    *   Server ရဲ့ **Destination Port** က Client ရဲ့ Firefox က အစကသုံးခဲ့တဲ့ **`51000`** ဖြစ်သွားပါမယ်။
3.  အဲဒီ packet ဟာ Client ကွန်ပျူတာဆီ ပြန်ရောက်လာတဲ့အခါ၊ Client ရဲ့ OS (Transport Layer) က packet header ကိုဖတ်ပြီး "ဪ၊ ဒါက Port `51000` ကို လာပို့တာပဲ" ဆိုတာ သိသွားပါတယ်။
4.  OS က "ဘယ် application က Port `51000` ကို သုံးနေတာလဲ?" လို့ စစ်ဆေးလိုက်တဲ့အခါ Firefox browser ဖြစ်နေတာကို တွေ့ရပါတယ်။ ဒါကြောင့် အဲဒီ data ကို Firefox process ဆီကိုသာ ပို့ပေးလိုက်ပါတယ်။ Netflix နဲ့ Skype တို့က တခြား port တွေကို သုံးနေတဲ့အတွက် ဒီ data ကို သူတို့ လုံးဝလက်ခံရရှိမှာ မဟုတ်ပါဘူး။

---

### **ထပ်မံသိရှိထားသင့်သော အရေးကြီးသည့် အချက်များ (Must-Know Knowledge)**

*   **Socket:** Socket ဆိုတာ ကွန်ရက်ပေါ်မှာ ဆက်သွယ်နေတဲ့ process တစ်ခုရဲ့ အဆုံးမှတ် (endpoint) ဖြစ်ပါတယ်။ Socket တစ်ခုကို **IP address နှင့် Port Number** နှစ်ခုပေါင်းပြီး သတ်မှတ်ပါတယ်။ ဥပမာ- `192.168.1.10:51000`။

*   **Port Numbers အမျိုးအစားများ:**
    *   **Well-known Ports (0 - 1023):** Server-side application တွေအတွက် ကြိုတင်သတ်မှတ်ထားတဲ့ port တွေပါ။ ဥပမာ- HTTP (80), HTTPS (443), FTP (21)။
    *   **Registered Ports (1024 - 49151):** တရားဝင်မှတ်ပုံတင်ထားတဲ့ application တွေသုံးတဲ့ port တွေပါ။
    *   **Dynamic/Private/Ephemeral Ports (49152 - 65535):** Client-side application တွေက request ပို့တဲ့အခါ ခဏတာသုံးဖို့ OS ကနေ ကျပန်းထုတ်ပေးတဲ့ port တွေပါ။

*   **TCP နှင့် UDP ၏ Demultiplexing ကွာခြားချက်:**
    *   **TCP Demultiplexing:** TCP က connection တစ်ခုကို မှတ်သားဖို့ အချက် **၄ ချက်** သုံးပါတယ်- Source IP, Source Port, Destination IP, Destination Port။ ဒီ ၄ ချက်လုံးတူမှ connection တစ်ခုတည်းလို့ သတ်မှတ်ပါတယ်။ ဒါကြောင့် web server တစ်လုံးကို client တွေအများကြီးက တစ်ပြိုင်နက်တည်း ချိတ်ဆက်တဲ့အခါ client တစ်ခုချင်းစီအတွက် သီးခြား socket တစ်ခုစီကို server က ဖန်တီးပေးနိုင်ပါတယ်။
    *   **UDP Demultiplexing:** UDP ကတော့ အချက် **၂ ချက်** ပဲသုံးပါတယ်- Destination IP, Destination Port။ ဘယ်သူပို့ပို့၊ Destination Port တူရင် socket တစ်ခုတည်းကိုပဲ data တွေ အကုန်ပို့ပေးပါတယ်။

**အနှစ်ချုပ်:** Multiplexing နဲ့ Demultiplexing ဟာ **Port Number** တွေကို အသုံးချပြီး ကွန်ပျူတာတစ်လုံးကနေ application အများအပြားကို တစ်ပြိုင်နက်တည်း ကွန်ရက်သုံးနိုင်အောင်၊ ပြီးတော့ ရောက်လာတဲ့ data တွေကို သက်ဆိုင်ရာ application ဆီကို မှန်ကန်စွာ ခွဲဝေပေးနိုင်အောင် စီမံခန့်ခွဲပေးတဲ့ Transport Layer ရဲ့ အလွန်အရေးပါတဲ့ လုပ်ငန်းစဉ်တစ်ခု ဖြစ်ပါတယ်။