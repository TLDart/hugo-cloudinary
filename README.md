# Hugo Cloudinary
![Static Badge](https://img.shields.io/badge/version-0.1-green)[![License: GPL v3](https://img.shields.io/badge/license-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)![Static Badge](https://img.shields.io/badge/requirements-%3E%3D0.90-orange)


A context-aware shortcode that allows the usage of Cloudinary CDN.

## Configuration

### Importing and using the module
```toml
[module]
[[module.imports]]
  path = 'github.com/TLDart/hugo-cloudinary'
```

### Parameters 

(In config.toml or hugo.toml)

#### Mandatory 
Mandatory parameters, necessary for the module to work correctly.
```toml
[params]
    baseURL = "https://res.cloudinary.com" # This is the same for everyone
    cloudName = "demo" # You can check your cloud name from cloudinary console page
```

#### Optional 
These parameters are not mandatory. If they are ommitted the values for each are shown below.
```toml
[params]
    imageExt = ["jpg", "webp", "jpeg", "png"] # Configures the extension list for images
    videoExt = ["mp4", "avi", "mkv", "wmv"] # Configures the extension list for videos
    LinkExt = ["pdf", "zip"] ## Configures the extension list for links
```
 

## Context Awareness

The shortcode is context-aware by creating the correct html element depending on the object passed in either **url** or **src**. If its an image type, it displays a figure with the image inside, it it is a video, it display said video using the \<video\> tag. Finally, if it is a file such as a pdf or zip, it displays it using a link (\<a\>). Furthermore, shortcode also allows the user to pass a its own css style using the "style" tag, css class using the "class" tag and 

## Modes of usage

### URL-Based

URL-Based mode assumes that the user provides a valid link (in this case, it needs no to be a cloudinary link, even thought it was the initial purpose) with a valid type. It supports the following parameters:
* **style** and  **class** - native CSS parameter;
* **alt** - native HTML paramter;
* **text** - works as a caption for an image or text for a link;
* **url** - (Mandatory) refers to full url of the resource;

#### Example

```hugo
{{< cloudinary url="https://res.cloudinary.com/demo/image/upload/sample.jpg" >}}
```

### Parameter-Based

Paramater-based mode assumes the usage of the previously set **baseUrl** and **cloudName** values. Those values are used to build dynamically build queries according to the parameters passed. It currently supports the following parameters:
* **style** and  **class** - native CSS parameter;
* **alt** - native HTML paramter;
* **text** - works as a caption for an image or text for a link;
* **src** - (Mandatory) refers to name of the resource;
Parameters related to Cloudinary transformations(refer to the original [Cloudinary Documentation](https://cloudinary.com/documentation/transformation_reference for more information):
* **angle**
* **audioCodec**
* **audioFrequency**
* **aspectRatio**
* **aspectRatio**
* **background**
* **border**
* **bitrate**
* **crop**
* **color**
* **colorSpace**
* **default**
* **delay**
* **density**
* **dpr**
* **duration**
* **effect**
* **endOffset**
* **format**
* **flag**
* **customFunction**
* **fps**
* **gravity**
* **height**
* **ifCondition**
* **keyframeInterval**
* **layer**
* **opacity**
* **prefix**
* **quality**
* **roundCorners**
* **startOffset**
* **streamingProfile**
* **namedTransformation**
* **underlay**
* **videoCodec**
* **videoSampling**
* **width**
* **xCoord**
* **yCoord**
* **zoom**

#### Example
```hugo
{{< cloudinary src="sheep.png" angle="45" background="lightblue" width="600" height="500" text="This is a caption">}}
```


## Live Demo
[TO BE ADDED]


