---
title: PKEY\_MFX\_KeywordDetector\_ProcessingModes\_Supported\_For\_Streaming
description: In Windows 10 and later, the PKEY\_MFX\_KeywordDetector\_ProcessingModes\_Supported\_For\_Streaming property key identifies the keyword detector mode effect processing modes supported for streaming supported by the driver.
ms.date: 11/28/2017
---

# PKEY\_MFX\_KeywordDetector\_ProcessingModes\_Supported\_For\_Streaming


In Windows 10 and later, the **PKEY\_MFX\_KeywordDetector\_ProcessingModes\_Supported\_For\_Streaming** property key identifies the keyword detector mode effect processing modes supported for streaming supported by the driver. The driver developer should list the keyword detector mode effect processing modes supported for streaming that their driver supports for the keyword detector pin.

This list only includes signal processing modes where the APO actually processes the audio signal during streaming. This list must not include any signal processing modes supported by the APO for discovery purposes only.

The INF file property key instructs the audio endpoint builder to set the CLSIDs for APOs into the effects property store. This information is used to build the audio graph that will be used to inform upper level apps what effects are in place.

## <span id="INF_File_Sample"></span><span id="inf_file_sample"></span><span id="INF_FILE_SAMPLE"></span>INF File Sample


An INF file specifies settings for an audio processing mode effect in the add-registry section for that device. The following INF example shows the strings and add-registry sections that loads the keyword detector mode effect processing modes into the registry.

```inf
[Strings]
PKEY_MFX_KeywordDetector_ProcessingModes_Supported_For_Streaming = "{D3993A3F-99C2-4402-B5EC-A92A0367664B},9"
...
AUDIO_SIGNALPROCESSINGMODE_DEFAULT = "{C18E2F7E-933D-4965-B7D1-1EEF228D2AF3}"
AUDIO_SIGNALPROCESSINGMODE_MOVIE   = "{B26FEB0D-EC94-477C-9494-D1AB8E753F6E}"
AUDIO_SIGNALPROCESSINGMODE_COMMUNICATIONS = "{98951333-B9CD-48B1-A0A3-FF40682D73F7}"
...
[SWAPAPO.I.Association0.AddReg]
;To register an APO for streaming in multiple modes, use a REG_MULTI_SZ property and include all the desired modes:
HKR,"FX\\0",%PKEY_MFX_KeywordDetector_ProcessingModes_Supported_For_Streaming%,%REG_MULTI_SZ%,%AUDIO_SIGNALPROCESSINGMODE_DEFAULT%,%AUDIO_SIGNALPROCESSINGMODE_MOVIE%,%AUDIO_SIGNALPROCESSINGMODE_COMMUNICATIONS%
```

## <span id="related_topics"></span>Related topics


[Media-Class INF Extensions](media-class-inf-extensions.md)

 

 






