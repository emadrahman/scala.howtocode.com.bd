<iframe src="https://www.facebook.com/plugins/likebox.php?href=https%3A%2F%2Fwww.facebook.com%2Fhowtocode.com.bd&amp;width&amp;height=62&amp;colorscheme=light&amp;show_faces=false&amp;header=false&amp;stream=false&amp;show_border=false&amp;appId=353725671441956" scrolling="no" frameborder="0" style="border:none; overflow:hidden; height:62px; margin-left:-15px;" allowTransparency="true"></iframe>

[কোর্স এর মুল পাতা](http://scala.howtocode.com.bd/) | [HowToCode মুল সাইট](http://www.howtocode.com.bd/) | [সবার জন্য প্রোগ্রামিং ব্লগ](http://blog.howtocode.com.bd/)

# Scala দি নেক্সট বিগ থিং

### [বজলুর রহমান রোকন](http://www.bazlur.com/)

### সংক্ষেপ

### স্ক্যালা- স্ক্যালেবল ল্যংগুয়েজ।

আপনি যদি ইতিমধ্যে জাভা প্রোগ্রামার হয়ে থাকেন, আপানকে সু-স্বাগতম। আশাকরি আপনাকে স্ক্যালা প্রোগ্রামিং এর সমুদ্রে পা ভেজানো চক্রান্তে আমি খানিকটা সফল। আর যদি না হয়ে থাকেন, তাহলে কোন কথাই নেই, 
সুপার-ডুপার ওয়েলকাম।

> ## Statutory warning
> __This material may have unexpected misspellings.  So readers are requested for feedback.__

### উপক্রমণিকা

আমি নিশ্চিত যে মোটামুটি ভাবে সবাই রড জনসন(Rod Johnson) কে চেনে। তাকে না চেনা খুব বড় অন্যায়, এখনি গুগুল করে জেনে নিন। তবে রড জনসনকে না চিনলেও স্প্রিং ফ্রেমওয়ার্ক এর নাম শুনেনি এমন লোক খুব কম পাওয়া যাবে।

একটা সময় ছিল যখন জাভা-এন্টারপ্রাইজ এপ্লিকেশান লেখা অনেক বেশি ক্লান্তিকর ছিল, তখন প্রথম আলো মুখ দেখায় রড জনসন তার "Expert One-on-One J2EE Development Without EJB” বইটি লিখে। তারপর পরের ইতিহাস সম্পূর্ণ ভিন্ন। জুন ২০০৩ এ স্প্রিং ফ্রেমওয়ার্ক এর প্রথম রিলিজ হয় এবং এর পর সারা পৃথিবীর মানুষ বিপুল উৎসাহে এই ফ্রেমওয়ার্ক ব্যবহার করে আছসে। JVM ওয়েব ফ্রেমওয়ার্ক গুলোর মধ্যে স্প্রিং সবার উপরে । রড জনসন হচ্ছে সেই স্প্রিং ফ্রেমওয়ার্ক এর জনক। VMWare ২০০৯ সালে SpringSource কিনে নেওয়া পর্যন্ত সেখানে সিইও হিসেবে দায়িত্ব পালন করে এসেছেন। তিনি বর্তমানে **Typesafe, Inc** এর বোর্ড অব ডিরেক্টর দের মধ্যে একজন।

যাহোক মূল কথায় ফিরে আসি,

ScalaDays 2013 Kaynote এ রড জনজন একটা বোল্ড মন্তব্য করেন। সেটি হলো -

>I believe in 2018 Scala will be the leading newer language. I believe its currently breaking out of pack of cycled second-tier languages and it will be the biggest things since Java.

আরো কিছু মন্তব্য -

>If I were to pick a language today other than Java, it would be Scala.

>-James Gosling(father of Java)


>I can honestly say if someone had shown me the Programming Scala book by Martin Odersky, Lex Spoon & Bill Venners back in 2003 I'd probably have never created Groovy.

>-James Strachan (creator of Groovy)

সুতরাং বুঝা যাচ্ছে, স্ক্যালা ইজ দি বিগ থিং। তো শুরু করা যাক।

প্রোগ্রামিং এর দুনিয়ায় মোটামুটিভাবে আমরা দুই ধরণের প্রোগ্রামিং সাথে বেশি পরিচিত-

১. ফাংশনাল প্রোগ্রামিং ২. অবজেক্ট ওরিয়েন্টেড প্রোগ্রামিং

দুটিরই ব্যপকতা অনেক। এদের মধ্যে মূল পার্থক্য হচ্ছে, ফাংশনার প্রোগ্রামিং এ ডাটা এক জায়গা থাকে, আর মেথড/ফাংশন গুলো অন্য কোথায় থাকে। আমরা ডাটা একসেস করি প্যাটার্ন ম্যাচিং এর মাধ্যমে। আর অবজেক্ট ওরিয়েন্টেড প্রোগ্রামিং মডেল বলে, এটি সম্পূর্ণ ভুুল, এটা মোটেও করা যাবে না। মেথড/ফাংশন গুলো সেখানেই রাখতে হবে যেখানে ডাটা রাখা আছে। এইভাবে দুটি কমিউনিটি আলাদা হয়ে যায়।

তবে এটা বলতে কারো আপত্তি নেই যে, দুটি প্রোগ্রামিং মডেল এর স্বপক্ষে ও বিপক্ষে যুক্তি আছে। মজার ব্যপার হলাে স্ক্যালা এমন একটি ল্যাংগুয়েজ যা এই দুটি কমিউনিটিকে এক করে দিতে সক্ষম হয়েছে। স্ক্যালা একি থাকে পিউর অবজেক্ট ওরিয়েন্টেড এবং সেই সাথে ফাংশনাল ল্যাংগুয়েজ। এটি কিভাবে সম্ভব সেটি নিয়ে অনেকেরই সন্দেহ থাকতে পারে, তবে ঘটনা সত্যি।

কিন্তু কেন স্ক্যালা শিখতে যাবো সেটা নিয়েও সংশয় থাকতেই পারে। আজকের এই লেখার মূল উদ্দেশ্য অবশ্য সেটাই। কেন স্ক্যালা এর উত্তর দেওয়া।

### সংক্ষেপে দীর্ঘ গল্প

স্ক্যালা অপেক্ষাকৃত নতুন প্রোগ্রামিং ল্যাংগুয়েজ, মাত্র ১০ বছর হয়েছে। এটি স্ট্যাটিক্যালী টাইপড এবং অবজেক্ট ওরিয়েন্টেড ও ফাংশনাল প্রোগ্রামিং ল্যাংগুয়েজ এর হাইব্রিড যা কিনা জাভা ভার্চুয়াল মেশিনে চলে (You know JMV languages are always hot (!))। খুব দ্রুত এটি জনপ্রিয় হয়ে যাচ্ছে (its getting hotter day by day)। এর বড় একটা কারণ হতে পারে কারণ এটি জাভার সব থেকে ভাল বিকল্প।

কেন ??

**১. স্ট্যাটিক্যালি টাইপড**

আমরা সাধারণত দুই ধরণের টাইপ সিস্টেম নিয়ে কথা বলে থাকি- স্ট্যাটিক্যালি টাইপড এবং ডাইনামিক্যালি টাইপড। দুই ধরণের ল্যাংগুয়েজের প্রয়োজনীয়তা দুই রকম। স্ট্যাটিক টাইপড ল্যাংগুয়েজ প্রত্যেকটি ভ্যারিয়্যবল আগে টাইপ ইনফরমেশন থাকতে হয়, সেটি টাইপ এবং অবজেক্ট দুটির ক্ষেত্রেই সত্য। উদাহরণ- Java-

	String myName = "Bazlur Rahman";

কিন্তু ডাইনামিক টাইপড ল্যাংগুয়েজ এর ক্ষেত্রে এর দরকার হয় না। যেমন – python -

	myName = "Bazlur Rahman"

স্যাটিক্যালি টাইপড সিস্টেমে কম্পাইলার কম্পাইল করার সময় সবকিছু চেক করে থাকে। যদি কোন ধরণের ইরর থাকে তাহলে সেগুলো কম্পাইল করার সময় ধরা পরে। অর্থাৎ কেও যদি ফ্লোাটিং পয়েন্ট ভ্যারিয়বল এ স্ট্রিং এসাইন করে ফেলে ভুল করে, তাহলে সেটি কম্পাইল করার সময়-ই ধরা পরবে, কিন্তু ডাইনামিক টাইপ সিস্টেম এ তা কম্পাইল টাইমে ধরা না পরে রান টাইম এ ধরা পরবে।

সহজ কথায়- স্ট্যাটিক টাইপ সিস্টেম ভাল কারণ এটি আপনাকে ঝামেলা থেকে দূরে রাখবে । আর ডাইনামি টাইপ সিস্টেম ভাল এটি আপানাকে আপনার মতো কাজ করতে দেবে এবং আপনি দ্রুত কাজ করতে পারবেন। সুতরাং আপনি নিজেই ঠিক করে নিন কোনটা আপনার জন্যে ভাল।

ব্যক্তিগত ভাবে আমি টাইপসেইফ প্রোগ্রামিং ল্যাংগুয়েজ এর গ্রেট ফ্যান। কারণ- কম্পাইলার কম্পাইল করার সময় সব ধরণে ধরনের বৈধতা যাচাই করে, এবং আপনি একটি ভ্যারিয়বলে ভুল টাইপ নির্ধারণ করার চেষ্টা করলেই আপনাকে সাথে সাথে জানিয়ে দেবে। যেহেতু আমি **Linus Torlvads** নই, সুতরাং আমি ভুল করতেই পারি।

স্যাটিক টাইপ সিস্টেম-এ অনেক সহজে এবং খুব বেশি চিন্তা ভাবনা না করেই কোড রিফ্যাক্টরিং করা যায়। ধরা যাক, একটা মেথড ইন্টিজার প্যারিমিটার নেই। আমি সেটা রিফ্যাক্টর করে স্ট্রিং করতে চাই। এবং সেটি করতে গিয়ে অনেক যায়গায় পরিবর্তন করতে হতে পারে। স্যাটিক টাইপ সিস্টেম এ কোড বেইজ শুধুমাত্র আবার রি-কম্পাইল করার সাথে সাথেই জেনে যাবো আর কোথায় কোথায় পরিবর্তন করতে হবে। মোট কথা - স্ট্যাটিক টাইপ আমাকে আমার পরিবর্তিত কোড যে ঠিক আগের মতই কাজ করবে তার যথেষ্ট নিশ্চয়তা প্রদান করে।

এ দিক থেকে স্ক্যালার টাইপ সিস্টেম অনেক বেশি উন্নত।

**Interoperability**

স্ক্যালা JVM ল্যাংগুয়েজ। এটি এমন ভাবে তৈরি করা হয়েছে যাতে করে Java-র সাথে সিমলেসলি কাজ করে পারে। স্ক্যালা সরাসরি Java-র ক্লাস, মেথড, ফিল্ডস কল করতে পারে এবং জাভা ক্লাস ইনহেরিট করতে পারে এমনকি জাভার ইন্টারফেইস ইম্প্লিমেন্ট করতে পারে। সুতরাং জাভার সমস্ত লাইব্রেরি স্ক্যালা ব্যবহার করতে পারে। এর থেকে বেশি Cool আর কি হতে পারে । 

**সংক্ষিপ্ত**

স্ক্যালা কোড সাধারণত খুব ছোট হয়। টিপিক্যালি একটি জাভা কোডকে স্ক্যালাতে লিখলে কোড অব লাইন অর্ধেক হয়ে যা। উদাহরণ-

    public class MyClass {
        private int index;
        private String name;
    
        public MyClass(int index, String name) {
            this.index = index;
            this.name = name;
        }
    }

এই সেইম কোড স্ক্যালতে হবে এক লাইন -

  	class MyClass(index: Int, name: String)

এই কোড হুবহু উপরের জাভা কোডটির মতই কাজ করে ।

ধরা যাক, আমি একটা স্ট্রিং ভ্যারিয়েবল এ আপার কেইস লেটার আছে কিনা সেটা বের করতে চাই-

আমরা যদি জাভাতে করতে চাই তাহলে -

    boolean hasUpperCaseLetter = false;
    
    for (int i = 0; i < name.length(); i++) {
        if (Character.isUpperCase(name.charAt(i))) {
            hasUpperCaseLetter = true;
            break;
        }
    }

কিন্তু সেই একই কোড স্ক্যালা তে করতে পারি এক লাইন এ -

    val hasUpperCaseLetter = name.exists(_.isUpper)

**Good parts from other languages**

স্ক্যালা মূলত অনেক গুলো ল্যাংগুয়েজ এর গুড পার্ট গুলো নিয়ে এবং অনেক দিনের গবেষণার ফসল। ইনোভেশান এর দিক থেকে স্ক্যালে খুব বেশি নতুন কিছু নেই, এর ফিচার গুলো অন্য কোন কোন ল্যাংগুয়েজ এ রয়েছে। কিন্তু স্ক্যালা এর উয়িন অন্য যায়। এটি মূলত সবগুলো গুড পার্ট এক যায়গায় সমন্বিত করা।

সিনট্যাক্স এর দিক থেকে স্ক্যালার বড় অংশ জাভা এবং সি শার্প থেকে ধার করা। এর মানে এর এটি সি এবং সি++ থেকেও ধার করেছে। রুবি এবং স্মলটক থেকে এর অবেজেক্ট মডেল ধার করা। মোট কথা- এটিতে অনেক গুলো ল্যাংগুয়েজ থেকে ভাল ভাল পার্ট গুলো নিয়ে একযায়গা সমন্বিত করা হয়েছে - যেমন - Algol, Simula, SML, Ocam, F#, ML, Haskell, Erlang, Java, C# etc.

**Type Inference**

স্ক্যালা তে চমৎকার টাইপ ইনফারেন্স সিস্টেম থাকায় অনেক ক্ষেত্রেই টাইপ ইনফরমেশান লিখতে হয় না। যেমন -

    val x = 1 + 2  // type Integer
    val y = x.toString // string type
    
    def increment(x: Int) = x + 1 //  method returns integer



### ওপেন সোর্স

এই বইটি মূলত স্বেচ্ছাশ্রমে লেখা এবং বইটি সম্পূর্ন ওপেন সোর্স । এখানে তাই আপনিও অবদান রাখতে পারেন লেখক হিসেবে । আপনার কন্ট্রিবিউশান গৃহীত হলে অবদানকারীদের তালিকায় আপনার নাম যোগ করে দেওয়া হবে ।

এটি মূলত একটি [গিটহাব রিপোজিটোরি](https://github.com/howtocode-com-bd/scala.howtocode.com.bd)  যেখানে এই বইয়ের আর্টিকেল গুলো মার্কডাউন ফরম্যাটে লেখা হচ্ছে । রিপোজটরিটি ফর্ক করে পুল রিকুয়েস্ট পাঠানোর মাধ্যমে আপনারাও অবদান রাখতে পারেন ।

<iframe src="https://www.facebook.com/plugins/like.php?href=http%3A%2F%2Fscala.howtocode.com.bd&amp;width&amp;layout=button_count&amp;action=like&amp;show_faces=false&amp;share=true&amp;height=21&amp;appId=353725671441956" scrolling="no" frameborder="0" style="border:none; overflow:hidden; height:21px;" allowTransparency="true"></iframe>
