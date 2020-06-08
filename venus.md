###Venus Feature
手势 -- Gesture
人脸106 -- Face106
人脸278 -- Face278
肢体 -- BodyLandmark
手相 -- Clothe-Segmentation
天空分割 -- Sky-Segmentation
头部分割 -- Head-Segmentation
头发分割 -- Hair-Segmentation
衣服分割 -- Clothe-Segmentation
背景分割 -- Background-Segmentation
### iOS/MacOS 新参数
```
    std::vector<std::string> appInfo;
    info.push_back("{Your-AppNme}");
    info.push_back("{Venus-Feature}");
    info.push_back("{Your-Platform}");
```

### Android 新参数
```
   String[] appInfo = {
                    "{Your-AppNme}",
                    "{Venus-Feature}",
                    "{Your-Platform}"
            };
```

### Demo
#### iOS
```
std::vector<std::string> appInfo;
    info.push_back("YYLive");
    info.push_back("Face106");
    info.push_back("iOS");
        {
        const int argc = 8;
        const char *argv[argc] = {            
            const_cast<const char *>([[[[[NSBundle mainBundle] bundlePath] stringByAppendingPathComponent:@"Models"] stringByAppendingPathComponent:@"face"] stringByAppendingPathComponent:@"face0.vnmodel"].UTF8String),
            const_cast<const char *>([[[[[NSBundle mainBundle] bundlePath] stringByAppendingPathComponent:@"Models"] stringByAppendingPathComponent:@"face"] stringByAppendingPathComponent:@"face1.vnmodel"].UTF8String),
            const_cast<const char *>([[[[[NSBundle mainBundle] bundlePath] stringByAppendingPathComponent:@"Models"] stringByAppendingPathComponent:@"face"]  stringByAppendingPathComponent:@"face2.vnmodel"].UTF8String),
            const_cast<const char *>([[[[[NSBundle mainBundle] bundlePath] stringByAppendingPathComponent:@"Models"] stringByAppendingPathComponent:@"face"]  stringByAppendingPathComponent:@"face3.vnmodel"].UTF8String),
            const_cast<const char *>([[[[[NSBundle mainBundle] bundlePath] stringByAppendingPathComponent:@"Models"] stringByAppendingPathComponent:@"face"]  stringByAppendingPathComponent:@"face4.vnmodel"].UTF8String),
            const_cast<const char *>([[[[[NSBundle mainBundle] bundlePath] stringByAppendingPathComponent:@"Models"] stringByAppendingPathComponent:@"face"]  stringByAppendingPathComponent:@"face5.vnmodel"].UTF8String),
            const_cast<const char *>([[[[[NSBundle mainBundle] bundlePath] stringByAppendingPathComponent:@"Models"] stringByAppendingPathComponent:@"face"]  stringByAppendingPathComponent:@"face6.vnmodel"].UTF8String),
            const_cast<const char *>([[[[[NSBundle mainBundle] bundlePath] stringByAppendingPathComponent:@"Models"] stringByAppendingPathComponent:@"face"]  stringByAppendingPathComponent:@"face7.vnmodel"].UTF8String),                                
        };
    VN_CreateFaceToolKit(&_handle, argc, (const void **)argv, VN_Detect_Video ,appInfo);
```
#### Android
```
String[] modelPath = {
                    sdcard + "/venus_face_data/model0.vnmodel",
                    sdcard + "/venus_face_data/model1.vnmodel",
                    sdcard + "/venus_face_data/model2.vnmodel",
                    sdcard + "/venus_face_data/model3.vnmodel",
                    sdcard + "/venus_face_data/model4.vnmodel",
                    sdcard + "/venus_face_data/model5.vnmodel",
                    sdcard + "/venus_face_data/model6.vnmodel",
                    sdcard + "/venus_smile_data/venus_smile_20200529.vnmodel"
            };
            String[] appInfo = {
                    "YYLive",
                    "Face106",
                    "Android"
            };
mVenusID = Venus.createFaceCpu(modelPath, Venus.VN_Detect_Mode.VN_Detect_Video,appInfo);
``` 

#### MacOS
```
    std::string mdFaceDetectionFile = "Venusmodels/face/face1.vnmodel";
    std::string mdFaceStnFile = "Venusmodels/face/face2.vnmodel";
    std::string mdFaceMainFile = "Venusmodels/face/face3.vnmodel";
    std::string mdFullyConnection = "Venusmodels/face/face4.vnmodel";
    std::string mdTrackingFile = "Venusmodels/face/face5.vnmodel";
    std::string mdFullyConnection_left = "Venusmodels/face/face6.vnmodel";
    std::string mdFullyConnection_right = "Venusmodels/face/face7.vnmodel";
    
    const char *argFaceDetection[] = { mdFaceDetectionFile.c_str(),
        mdFaceStnFile.c_str(),
        mdFaceMainFile.c_str(),
        mdFullyConnection.c_str(),
        mdTrackingFile.c_str(),
        mdFullyConnection_left.c_str(),
        mdFullyConnection_right.c_str() };
    
    std::vector<std::string> appInfo;
    info.push_back("Venus");
    info.push_back("Face106");
    info.push_back("MacOS");
    
    VN_CreateFaceDetection_CPU(&s_faceDetectionID, 7, (const void**)argFaceDetection,appInfo)
``` 