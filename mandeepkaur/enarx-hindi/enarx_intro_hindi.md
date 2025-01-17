# एनरक्स: गोपनीय कंप्यूटिंग के लिए एक प्रमुख ओपन सोर्स प्रोजेक्ट


## संक्षेप

संवेदनशील कोड या डेटा वाले संगठनों को अपने अनुप्रयोगों को मजबूत अखंडता और गोपनीयता सुरक्षा के साथ चलाने की आवश्यकता होती है, खासकर जब क्लाउड या एज पर तैनात किया जाता है। एनरक्स एक ओपन सोर्स प्रोजेक्ट है जो टीईई (ट्रस्टेड एक्ज़ीक्यूशन एनवायरनमेंट) का संगठनों को एप्लिकेशन चलाने और उन सिस्टम पर गोपनीय डेटा को संसाधित करने में सक्षम बनाता है जिन पर वे भरोसा नहीं करते हैं।

        
## भूमिका   

चूंकि विभिन्न क्षेत्रों के संगठन अपने कंप्यूटिंग वर्कलोड को कई वातावरणों में, ऑन-प्रिमाइसेस से सार्वजनिक क्लाउड से एज तक ले जाते हैं, इसलिए उन्हें अधिक आश्वासन की आवश्यकता होती है कि उनका संवेदनशील कोड और डेटा सुरक्षित है। यह बैंकिंग और वित्त जैसे क्षेत्रों के लिए विशेष रूप से सच है; सरकार और सार्वजनिक क्षेत्र; दूरसंचार; इंटरनेट ऑफ थिंग्स (IoT); स्वास्थ्य (जैसे एचआईपीएए); ग्राहक डेटा (जैसे जीडीपीआर); संवेदनशील उद्यम कार्य; रक्षा; और मानवाधिकार।

ऐसे तीन चरण हैं जिनमें डेटा को संरक्षित किया जा सकता है: रेस्ट में  , ट्रांज़िट में और उपयोग में। बाकी डेटा में फ़ाइलें, ऑब्जेक्ट और स्टोरेज शामिल हैं। ट्रांज़िट में डेटा में वह डेटा शामिल होता है जो एक स्थान से दूसरे स्थान पर जाता है जैसे कि पूरे इंटरनेट या निजी नेटवर्क पर। उपयोग में डेटा वह डेटा है जिसे सीपीयू या रैम में संसाधित किया जा रहा है। क्लाउड कंप्यूटिंग में रेस्ट और ट्रांज़िट में डेटा एन्क्रिप्ट करना एक आदर्श बन गया है, लेकिन उपयोग में डेटा अभी भी एक उभरती हुई चिंता है।

सार्वजनिक क्लाउड में कार्यभार चलाते समय, या तो वीएम या कंटेनर के रूप में, कार्यभार को किसी भी व्यक्ति या सॉफ़्टवेयर द्वारा होस्ट सिस्टम तक पहुंच के साथ छेड़छाड़ किए जाने की संभावना होती है। भले ही क्लाउड प्रदाता की सख्त सुरक्षा नीतियां हों, ऑपरेटिंग सिस्टम, फर्मवेयर लाइब्रेरी, हाइपरवाइजर, एप्लिकेशन स्टैक, थर्ड पार्टी लाइब्रेरी, मिडलवेयर और ड्राइवरों सहित होस्ट सिस्टम के साथ समझौता किए जाने पर भी वर्कलोड अतिसंवेदनशील होता है।


ट्रस्टेड एक्ज़ीक्यूशन एनवायरनमेंट(टीईई) उपयोग में डेटा गोपनीयता और अखंडता बनाए रखने के  इस आवश्यकता के लिए एक हार्डवेयर-आधारित समाधान प्रदान करते हैं, इस बात की परवाह किए बिना कि भले ही उस होस्ट सिस्टम का मालिक हो या होस्ट सिस्टम तक पहुंच हो, जिस पर एप्लिकेशन चल रहा है।

## पृष्ठभूमि

ट्रस्टेड एक्ज़ीक्यूशन एनवायरनमेंट (टीईई) संगठनों को मेमोरी पेजों के एक सेट के भीतर एप्लिकेशन चलाने की अनुमति देता है जो होस्ट सीपीयू द्वारा एक गुप्त कुंजी के साथ एन्क्रिप्ट किए जाते हैं ताकि ये पेज ऑपरेटिंग सिस्टम या किसी अन्य सॉफ़्टवेयर के लिए सुलभ न हों, भले ही उच्चतम विशेषाधिकार स्तर पर भी चल रहा है।

`वर्तमान में टीईई के दो प्रमुख मॉडल हैं:`

`प्रक्रिया-आधारित`: इस मॉडल में, एक प्रक्रिया को दो घटकों में विभाजित किया जाता है: विश्वसनीय और अविश्वसनीय। विश्वसनीय घटक एन्क्रिप्टेड मेमोरी में रहता है और गोपनीय कंप्यूटिंग को संभालता है, जबकि अविश्वसनीय घटक ऑपरेटिंग सिस्टम के साथ इंटरफेस करता है और आई /ओ  को एन्क्रिप्टेड मेमोरी से बाकी सिस्टम में प्रसारित करता है। डेटा केवल पूर्वनिर्धारित चैनलों के माध्यम से इस एन्क्रिप्टेड क्षेत्र में प्रवेश और बाहर निकल सकता है, जिसमें से गुजरने वाले डेटा के आकार और प्रकार पर सख्त जांच होती है। प्रक्रिया-आधारित दृष्टिकोण के वर्तमान कार्यान्वयन में इंटेल का एसजीएक्स( SGX -सॉफ़्टवेयर गार्ड एक्सटेंशन) शामिल है।

`वीएम-आधारित`: इस मॉडल में, मेमोरी को वीएमएम के शीर्ष पर चलने वाली पारंपरिक वीएम सीमा के साथ एन्क्रिप्ट किया गया है। जबकि पारंपरिक वीएम (साथ ही कंटेनर) अलगाव के कुछ उपाय प्रदान करते हैं, इस टीईई मॉडल में वीएम हार्डवेयर-आधारित एन्क्रिप्शन कुंजी द्वारा संरक्षित होते हैं जो दुर्भावनापूर्ण वीएमएम द्वारा हस्तक्षेप को रोकते हैं। वर्तमान कार्यान्वयन में एएमडी का एसईवी (सिक्योर एनक्रिप्टेड वर्चुअलाइजेशन) शामिल है।

टीईई में चलाने के लिए आवश्यक अनुप्रयोगों को विशेष रूप से प्रत्येक प्लेटफॉर्म के लिए विकसित किया जाना चाहिए, और वे प्रक्रिया-आधारित या वीएम-आधारित टीईई मॉडल के आधार पर काफी भिन्न होते हैं। इसके अतिरिक्त, उन्हें सत्यापन नामक कुछ लागू करना होगा, जो कि टीईई के लिए एक सत्यापन प्रक्रिया है जो यह साबित करने के लिए है कि यह वास्तविक है इससे पहले कि यह आवेदन द्वारा भरोसा किया जा सके। प्रत्येक हार्डवेयर प्लेटफॉर्म के लिए एप्लिकेशन या कस्टम वीएमएम को फिर से लिखना, साथ ही साथ सत्यापन, अत्यंत जटिल और समय लेने वाला है।




अगले भाग में, हम एनरक्स को पेश करेंगे, जो टीईई में एप्लिकेशन चलाने के लिए एक ओपन सोर्स फ्रेमवर्क है जो उठाए गए कई मुद्दों को संबोधित करता है। हम एनरक्स के कंपोनेंट आर्किटेक्चर (और यह कैसे कई हार्डवेयर प्लेटफॉर्म के लिए समर्थन की अनुमति देता है) और एनरक्स का उपयोग करके टीईई इंस्टेंस के लिए एप्लिकेशन बनाने और तैनात करने की प्रक्रिया का सरलीकृत अवलोकन देंगे।

## एनरक्स

एनरक्स टीईई उदाहरणों में एप्लिकेशन चलाने के लिए एक ढांचा है - जिसे हम "कीप" के रूप में संदर्भित करते हैं - सत्यापन को अलग से लागू करने की आवश्यकता के बिना, बहुत सारी निर्भरताओं पर भरोसा करने की आवश्यकता के बिना, और एप्लिकेशन को फिर से लिखने की आवश्यकता के बिना। यह वासम्मटाइम  के आधार पर एक वेबसेमब्ली रनटाइम प्रदान करता है। यह उपयोगकर्ता के लिए पारदर्शी रूप से सिलिकॉन आर्किटेक्चर में काम करने के लिए डिज़ाइन किया गया है ताकि एप्लिकेशन इंटेल प्लेटफॉर्म (एसजीएक्स या हाल ही में घोषित टीडीएक्स), एएमडी प्लेटफॉर्म (एसईवी) या आने वाले प्लेटफॉर्म जैसे आर्म्स रियलम्स और आईबीएम के पीईएफ पर समान रूप से सरल रूप से चल सके। सभी एप्लिकेशन कोड को पुन: संकलित किए बिना।

एनरक्स का उद्देश्य अनुप्रयोगों को निष्पादित करते समय आवश्यक विश्वास संबंधों को कम करना है, जिसका अर्थ है कि केवल  जिन घटकों पर भरोसा करने की आवश्यकता है वे हैं: सपयु(  CPU) और संबंधित फर्मवेयर, स्वयं कार्यभार, और एनरक्स मिडलवेयर, जो पूरी तरह से खुला स्रोत और लेखापरीक्षा योग्य है। एप्लिकेशन स्टैक स्टैक में कोई भी परत(जैसे हाइपरवाइजर, कर्नेल, यूजर-स्पेस)  "कीप"  या उसकी सामग्री में देखने या बदलने में सक्षम नहीं होते हैं।

एनरक्स उपयोगकर्ता के लिए पारदर्शी तरीके से होने वाले एप्लिकेशन का अनुप्रमाणन, पैकेजिंग और प्रावधान प्रदान करता है। किसी एप्लिकेशन का प्रत्येक उदाहरण तीन चरणों से गुजरता है:

`अनुप्रमाणन`: एनरक्स जाँचता है कि जिस होस्ट को आप तैनात करने की योजना बना रहे हैं वह एक वास्तविक टीईई उदाहरण है।

`पैकेजिंग`: एक बार अनुप्रमाणन पूरा हो जाने और टीईई इंस्टेंस सत्यापित होने के बाद, एनरक्स प्रबंधन घटक किसी भी आवश्यक डेटा के साथ एप्लिकेशन को एन्क्रिप्ट करता है।

`प्रावधन`: एनरक्स तब एनरक्स कीप में निष्पादन के लिए होस्ट के साथ एप्लिकेशन और डेटा भेजता है। किसी भी समय  पर होस्ट सिस्टम, एप्लिकेशन या डेटा को अंदर देखने या बदलने में सक्षम नहीं है।




एनरक्स, वेबसेमब्ली पर आधारित एक रन-टाइम "कीप" में अनुप्रमाणन और वितरण को संभालता है, डेवलपर्स को कार्यान्वयन के लिए भाषा विकल्पों की एक विस्तृत श्रृंखला प्रदान करता है। कीप का रन-टाइम Rust, C, C++, C#, Go, Java, Python और Haskell जैसी भाषाओं में लिखे गए एप्लिकेशन को स्वीकार कर सकता है। एनरक्स सीपीयू-आर्किटेक्चर स्वतंत्र है, एक ही एप्लिकेशन कोड को कई लक्ष्यों में तैनात करने में सक्षम बनाता है, ताकि हार्डवेयर विक्रेताओं  क्रॉस-संकलन और अलग-अलग अनुप्रमाणन तंत्र जैसे मुद्दों से दूर रहें।

## निष्कर्ष
एनरक्स एक ओपन सोर्स प्रोजेक्ट है जो टीईई (ट्रस्टेड एक्ज़ीक्यूशन एनवायरनमेंट) का उपयोग करता है ताकि सिस्टम पर "कीप्स" के भीतर चल रहे एप्लिकेशन की अनुमति दी जा सके जो विश्वसनीय नहीं हैं। एनरक्स इन कीप्स के निर्माण का प्रबंधन करता है, क्रिप्टोग्राफ़िक विश्वास प्रदान करता है कि कीप्स वैध CPU हार्डवेयर का उपयोग कर रहे हैं और फिर एक बार की क्रिप्टोग्राफ़िक कुंजियों का उपयोग करके कीप में एप्लिकेशन और डेटा को एन्क्रिप्ट और प्रोविज़न करना।  एप्लिकेशन स्टैक स्टैक में कोई भी परत (जैसे हाइपरवाइजर, कर्नेल, यूजर-स्पेस, मिडलवेयर) कीप में देखने में सक्षम नहीं होते हैं। यह पोर्टेबिलिटी के बारे में चिंता किए बिना विभिन्न CPU निर्माताओं से टीईई पर चलने की अनुमति देता है: एनरक्स सत्यापन और परिनियोजन के साथ इसका प्रबंधन करता है।

