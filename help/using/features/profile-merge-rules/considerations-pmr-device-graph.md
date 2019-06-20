---
description: 請避免對沒有任何即時區段人口群的區段使用「裝置圖表」的「設定檔合併規則」。
seo-description: 請避免對沒有任何即時區段人口群的區段使用「裝置圖表」的「設定檔合併規則」。
seo-title: 設定檔合併規則與裝置圖表的重要考量
title: 設定檔合併規則與裝置圖表的重要考量
uuid: 93cd8861-210d-4c52-9cb7-1f2dd7dc7dc018a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Important Considerations for Profile Merge Rules with Device Graphs {#important-considerations-for-profile-merge-rules-with-device-graphs}

Avoid using [!UICONTROL Profile Merge Rules] with a [!UICONTROL Device Graph] for segments which have little to no real-time segment population.

>[!IMPORTANT]
>
>If the [!UICONTROL Profile Merge Rule] is configured incorrectly, the segment population exported to batch destinations may be significantly lower than expected.

Segments using a [Profile Merge Rule with a Device Graph](../../features/profile-merge-rules/merge-rule-targeting-options.md#device-graph-options) are only evaluated against devices seen in real-time on [Audience Manager’s Edge Servers](../../reference/system-components/components-edge.md) after the segment has been created.

Remember, a [!UICONTROL Profile Merge Rule] with a [!UICONTROL Device Graph] has one of the following device options selected, as shown below.

![](assets/pmr-considerations-1.png)

Devices that qualify for a segment in real-time are measured by the [segment’s real-time population](../../features/segments/segment-builder-data.md#segment-populations).

![](assets/pmr-considerations-2.png)

低即時區段人口族群意味著即時檢視區段的裝置很少。For best performance, segments with little to no real-time population should use a [!UICONTROL Profile Merge Rule] set to evaluate the *[!UICONTROL Current Device]*, like in the image below.

![](assets/pmr-considerations-3.png)

Setting the [!UICONTROL Profile Merge Rule] to evaluate the *[!UICONTROL Current Device]* ensures that all devices (not just those seen in real-time) are evaluated for the segment. 所有符合區段的裝置均由區段總人口定義，如下所示。

![](assets/pmr-considerations-4.png)