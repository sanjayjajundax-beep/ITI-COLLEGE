MY STUDY DIARY — PWA + ANDROID APK तैयारी

1) इस पूरे फोल्डर की सभी फाइलें GitHub/Cloudflare Pages के उसी प्रोजेक्ट रूट में अपलोड करें।
2) HTTPS URL खोलें और Chrome में Install app / Add to Home screen चुनें।
3) Android APK के लिए यही प्रकाशित HTTPS URL PWABuilder (pwabuilder.com) में डालकर Android package बनाएं। APK को अपने फोन पर जांचने के बाद WhatsApp से साझा करें।

ऑफलाइन व्यवहार:
- पहली बार Firebase से ऑनलाइन जुड़ना और Anonymous Authentication सफल होना जरूरी है।
- उसके बाद ऐप की उपलब्ध लोकल कॉपी और IndexedDB डेटा से डायरी/टॉपिक/मॉक टेस्ट एंट्री ऑफलाइन सेव की जा सकती हैं।
- इंटरनेट लौटने पर pending changes उसी Firebase anonymous UID के अंतर्गत सिंक होते हैं।
- ऐप डेटा डिवाइस/ब्राउज़र के लोकल स्टोरेज में रहता है; ऐप डेटा/ब्राउज़र डेटा साफ करने से पहले ऑनलाइन सिंक कर लें।

महत्वपूर्ण Firebase बात:
मौजूदा Firebase project/config और users/{uid}/... paths को बदला नहीं गया है। पुराने वेब ऐप का डेटा तभी उसी खाते में दिखेगा जब नया ऐप उसी origin/browser storage में वही anonymous UID रखे। अलग APK WebView/TWA origin में नया UID बन सकता है और डेटा अलग दिखाई दे सकता है। पहले APK को सीमित परीक्षण में जांचें। Anonymous Auth और Firestore Rules की जांच करें; Admin SDK key कभी client में न रखें।

यह पैकेज PWA assets और offline queue देता है; signed APK binary इस पैकेज में शामिल नहीं है। APK PWABuilder से बनाना होगा।
