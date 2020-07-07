# ডিকশনারি

এর আগে আমরা লিস্ট সম্পর্কে জেনেছি যেটা এমন এক ধরণের ডাটা স্ট্রাকচার যার মধ্যে এলিমেন্ট গুলো ক্রমিক ইনডেক্স অনুযায়ী সাজানো থাকে। ডিকশনারি আরেক ধরণের ডাটা স্ট্রাকচার যার মধ্যেও লিস্টের মত বিভিন্ন রকম এলিমেন্ট বা অবজেক্ট স্টোর করা যায় - কিন্তু, এ ক্ষেত্রে ওই এলিমেন্ট গুলোকে ম্যানুয়ালি ইনডেক্স করতে হয়। অন্যভাবে বলতে গেলে, আমাদের নিজেদেরকেই প্রত্যেকটা এলিমেন্টের বা value এর জন্য একটি key বা ইনডেক্স নির্ধারণ করে দিতে হয়। অতঃপর একটি key-value জোড় ওয়ালা এলিমেন্টের কালেকশন তৈরি হয়।

দুটি কার্লী ব্র্যাকেট `{}` এর মধ্যে কোলন চিহ্ন দিয়ে key-value জোড় তৈরি করে এবং প্রত্যেক জোড় কে কমা `,` দিয়ে আলাদা করে একটি ডিকশনারি তৈরি করা যায়। নিচের মত করে।

```python
my_marks = {"Bengali": 80, "English": 85, "Math": 90}
```

আবার ফাকা ডিকশনারি তৈরির জন্য এভাবে লিখলেই সেটি ইনিসিয়ালাইজ হয়ে যায় - `my_dictionary = {}`

ডিকশনারির প্রত্যেকটি এলিমেন্টকে অ্যাক্সেস করার নিয়ম লিস্টের মতই। লিস্টে যেমন থার্ড ব্র্যাকেট এর মধ্যে ইনডেক্স দিয়ে উক্ত ইনডেক্সের ভ্যালু পাওয়া যেত, তেমনি এর ক্ষেত্রেও ইনডেক্সের যায়গায় key ব্যবহার করে, এর সাথে জোড় হিসেবে থাকা ভ্যালুটাকে অ্যাক্সেস করা যাবে।

উদাহরণ,

```python
my_marks = {"Bengali": 80, "English": 85, "Math": 90}
print(my_marks["Math"])
```

আউটপুট,

```python
90
```

**কি - ভ্যালুর নিয়ম**  
ডিকশনারির মধ্যে যেকোনো টাইপের অবজেক্ট বা এলিমেন্টকেই স্টোর করা যায় শুধু মাত্র এর key গুলো হতে হবে Immutable \(অপরিবর্তনীয়\) টাইপের যেমন নিচের মত করে একটি ডিকশনারি তৈরি করা যেতে পারে -

```python
my_marks = {"Bengali" : [30, 35, 32], "English" : [45, 52, 33], "Math": [60, 74, 58]}
```

অর্থাৎ প্রত্যেকটি key এর সাপেক্ষে ভ্যালু গুলো হচ্ছে এক একটি লিস্ট। এই ডিকশনারি থেকে নিচের মত করে ডাটা অ্যাক্সেস করা যাবে -

```python
my_marks = {"Bengali" : [30, 35, 32], "English" : [45, 52, 33], "Math": [60, 74, 58]}
print(my_marks["Math"])
```

যার আউটপুট আসবে,

```python
[60, 74, 58]
```

কিন্তু নিচের মত একটি ডিকশনারি হতে পারে না -

```python
my_marks = {[30, 35, 32] : "Bengali", [45, 52, 33] : "English", [60, 74, 58] : "Math"}
```

এর আউটপুট হবে,

```python
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list'
```

অর্থাৎ একটি লিস্ট যা কিনা একধরনের Mutable টাইপ তাকে কোন ডিকশনারির key হিসেবে ব্যবহার করা যাবে না। মজার জন্য চেক করতে পারি, যেহেতু bool টাইপও Immutable তাই নিচের মত একটা ডিকশনারিও কিন্তু হতে পারে -

```python
my_marks = {True : "Bengali"}
```

> এখন পর্যন্ত আমাদের আলোচিত অবজেক্ট গুলোর মধ্যে লিস্ট এবং ডিকশনারি হচ্ছে Mutable টাইপের
