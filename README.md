PinYin4Objc
===========

PinYin4Objc is a popular Objective-C library supporting conversion between Chinese(both Simplified and Traditional) characters and most popular Pinyin systems，it's performance is very efficient, data cached at first time, you can use async method with block, this can avoid UI blocking, and runs smoothly. The output format of pinyin can be customized. 

*Updates*:

2013-10-08, V1.1, add async methods whit block, solve ui blcoking problems and fix some cache bugs;
2013-09-16, V1.0, firt virsion published.
  
## Usage
1. Use async method with block, this can avoid ui blocking, and runs smoothly:

```objc
NSString *sourceText=@"我爱中文";
HanyuPinyinOutputFormat *outputFormat=[[HanyuPinyinOutputFormat alloc] init];
[outputFormat setToneType:ToneTypeWithoutTone];
[outputFormat setVCharType:VCharTypeWithV];
[outputFormat setCaseType:CaseTypeLowercase];    
[PinyinHelper toHanyuPinyinStringWithNSString:sourceText 
				   withHanyuPinyinOutputFormat:outputFormat 
								   withNSString:@" " 
								   outputBlock:^(NSString *pinYin) {
	_outputTv.text=pinYin; //update ui

 }];
```

2. Use sync  method below:

```objc
NSString *sourceText=@"我爱中文";
HanyuPinyinOutputFormat *outputFormat=[[HanyuPinyinOutputFormat alloc] init];
[outputFormat setToneType:ToneTypeWithoutTone];
[outputFormat setVCharType:VCharTypeWithV];
[outputFormat setCaseType:CaseTypeLowercase];
NSString *outputPinyin=[PinyinHelper toHanyuPinyinStringWithNSString:sourceText withHanyuPinyinOutputFormat:outputFormat withNSString:@" "];
``` 	


## ScreenShot

   ![ScreenShot](ScreenShot.PNG)