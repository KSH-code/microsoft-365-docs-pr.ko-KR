---
title: 콘텐츠 검색을 사용하여 타사에서 가져온 데이터 검색
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: 콘텐츠 검색 eDiscovery 도구를 사용하여 쿼리를 만들어 타사 Microsoft 365 원본의 사서함으로 가져온 항목을 검색할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 068a6e3164154129ba9148b41138d50c518042ed
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202982"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a>콘텐츠 검색을 사용하여 사용자 지정 파트너 커넥터에서 가져온 타사 데이터 검색

콘텐츠 검색 [eDiscovery](content-search.md) 도구를 사용하여 Microsoft 365 규정 준수 센터 원본의 사서함으로 가져온 항목을 Microsoft 365 타사 데이터 원본에서 검색할 수 있습니다. 가져온 모든 타사 데이터 항목을 검색하는 쿼리를 만들거나 특정 타사 데이터 항목을 검색하는 쿼리를 만들 수 있습니다. 또한 쿼리 기반 보존 정책 또는 쿼리 기반 eDiscovery 보류를 만들어 타사 데이터를 보존할 수도 있습니다.
  
파트너와 협력하여 타사 데이터를 가져오는 데 사용할 수 있는 타사 데이터 형식 및 타사 데이터 형식 목록을 Microsoft 365 파트너와 협력하여 타사 데이터를 [Office 365.](work-with-partner-to-archive-third-party-data.md)

> [!IMPORTANT]
> 이 문서의 지침은 사용자 지정 파트너 커넥터에서 가져온 타사 데이터에만 적용됩니다. 이 문서는 Microsoft 규정 준수 센터의 타사 데이터 [](archiving-third-party-data.md#third-party-data-connectors) 커넥터를 사용하여 가져온 타사 데이터에는 적용되지 않습니다.
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>모든 타사 데이터를 검색하는 쿼리 만들기

콘텐츠 검색으로 가져온 모든 유형의 타사 데이터를 검색(또는 보류Office 365 콘텐츠 검색의 키워드 상자에 또는 쿼리 기반 보류를 만들 때 메시지 속성 값 쌍을 사용할 수 `kind:externaldata` 있습니다. 예를 들어 타사 데이터 원본에서 가져온 항목을 검색하고 가져온 항목의 Subject 속성에 "contoso"라는 단어를 포함하기 위해 다음 쿼리를 사용합니다. 
  
```powershell
kind:externaldata AND subject:contoso
```

이전 키워드 쿼리 예제에는 제목 속성이 포함되어 있습니다. 키워드 쿼리에 포함할 수 있는 타사 데이터 항목에 대한 다른 속성 목록은 파트너와 협력하여 타사 데이터를 [Office 365.](work-with-partner-to-archive-third-party-data.md#more-information)
  
타사 데이터를 검색하고 보유하는 쿼리를 만들 때 조건을 사용하여 검색 결과 범위를 좁힐 수도 있습니다. 콘텐츠 검색 쿼리를 만드는 데 대한 자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건을 참조하세요.](keyword-queries-and-search-conditions.md)
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>특정 유형의 타사 데이터를 검색하는 쿼리 만들기

모든 유형의 타사 데이터를 검색하는 대신 콘텐츠 검색에 대한 키워드 상자의 값 쌍을 사용하여 특정 형식의 타사 데이터만 검색하는 쿼리를 만들 수 있습니다. 
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

예를 들어 Subject 속성에 단어 "contoso"가 포함된 Facebook 데이터를 검색하기 위해 다음 쿼리를 사용합니다.
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

다음 표에는 검색할 수 있는 타사 데이터 형식과 메시지 속성에서 해당 형식의 타사 데이터를 구체적으로 검색하는 데 사용할  `itemclass:` 값이 나열됩니다. 쿼리 구문은 대소문자 구분이 없습니다. 
  
|**타사 데이터 형식**|**속성  `itemclass:` 값**|
|:-----|:-----|
|AIM  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL with Pivot Client   <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|Ares  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Axs Placeholder  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|바자르보ice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|Bearshare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|Blackberry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|BlackBerry 통화 로그  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry Messenger  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry PIN  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry SMS  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|블룸버그 메시지  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|Bloomberg Messaging  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Box  <br/> | `ipm.externaldata.Box*` <br/> |
|Cisco IM &amp; Presence Server  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud for Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Direct Connect  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google+  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google Talk  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|IBM Connections  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|ICE 채팅  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|Indii Messenger  <br/> | `ipm.externaldata.Indii*` <br/> |
|인스 타마  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|IRC  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|JXTA  <br/> | `ipm.externaldata.JXTA*` <br/> |
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|Microsoft UC  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|Mind Align  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|MSN  <br/> | `ipm.externaldata.MSN*` <br/> |
|MySpace  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|OpenNap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|Pinterest  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|Pivot  <br/> | `ipm.externaldata.Pivot*` <br/> |
|QQ  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|비즈니스용 Skype  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack Enterprise Grid  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|SoftEther  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|스쿼워커  <br/> | `ipm.externaldata.Squawker*` <br/> |
|Symphony  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|UBS Chat  <br/> | `ipm.externaldata.UBS*` <br/> |
|Vimeo  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo!  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
