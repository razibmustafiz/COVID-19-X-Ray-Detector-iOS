---
services: cognitive-services,custom-vision
platforms: Objective-C, iOS
author: Razib Mustafiz
---

# COVID-19 Chest X-Ray Detector: A Real-time iOS Application

This repository contains the project file needed to compile the iOS application for a Realtime Smartphone based COVID-19 chest X-Ray detector. You can download the project folder to your MAC and than load it to your Xcode environment. This iOS project contains Tensorflow CNN model trained on thousands of X-Ray data from well curated and trusted repositories.It is trained to detect COVID-19 Chest X-Ray from Normal and Normal Viral Pneumonia infected Chest X-Ray images.

This Mobile Application version of the COVID-19 detection system is a lightweight inference system designed to be used in a rural area where internet connection is not reliable or not available at all. Server dependent application architecture is not an ideal solution in this circumstances. That’s why we came up with a solution where AI engine will run locally in the Mobile device and will do real time X-Ray image prediction with its on device hardware. However, prediction result will greatly very with device’s camera quality and processor power since the AI engine runs locally. We suggest to use not less than iPhone 7.

This is a Research project and is not intended to use in real life scenario.Further studies and experimentation required for practical application.



This iOS application demonstrates how to take a trained model exported from the [Custom Vision Service](https://www.customvision.ai) in the CoreML format and add it to an application for real-time image classification. 

## Getting Started

### Prerequisites

- [XCode 10](https://developer.apple.com/xcode/)
- [CocoaPods](https://cocoapods.org)
- iOS device running iOS 11 or later

### Quickstart

1. Clone the repository
2. Run `pod install`
3. Open the xcworkspace `CVS_ClassifierSample` in Xcode
4. Build and run the sample on your iOS device



### Compatibility

This latest sample application relies on the new iOS library *Custom Vision inference run-time* (or simply *run-time*) to take care of compatibility. It handles:

- __Version check__: Check the version of the exported model by looking at `cvexport.manifest` (more specifically, look for *ExporterVersion* field) and switch logic depending on model version.

    - __Fowrard compatibility__: It is when model version is newer than run-time's maximum supported model version.
    
        - Major version is greater: Throw exception (supposing model format is unknown)

        - Major version is same but minor version is greater: Still works. Run inference.

    - __Backward compatiblity__: Any newer version of the run-time should be able to handle older model versions.

#### Supported model versions

| Run-time version  | Model version |
|--:                |--             |
| Run-time 1.0.0    | Work with model version 1.x |
|                   | Work with model version 2.x |
|                   | Not work with model version 3.0 or higher |


## Resources
- Link to [CoreML documentation](https://developer.apple.com/documentation/coreml)
- Link Apple WWDC videos, samples, and materials for information on [CoreML](https://developer.apple.com/videos/play/wwdc2017/710) and [Vision Framework](https://developer.apple.com/videos/play/wwdc2017/506/)
- Link to [Custom Vision Service Documentation](https://docs.microsoft.com/en-us/azure/cognitive-services/custom-vision-service/home)

