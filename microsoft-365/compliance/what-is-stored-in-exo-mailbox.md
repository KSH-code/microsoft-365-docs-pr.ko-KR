---
title: 사서함에 Exchange Online 콘텐츠
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
description: 클라우드 기반 앱에서 생성하는 콘텐츠는 Microsoft 365 사서함에 저장되거나 Exchange Online 연결됩니다. 이 콘텐츠는 Microsoft eDiscovery 도구를 사용하여 검색할 수 있습니다.
ms.openlocfilehash: 975f4ac8be8c2cdeed8dea1d73699607662a1ce9
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216142"
---
# <a name="content-stored-in-exchange-online-mailboxes-for-ediscovery"></a>eDiscovery의 Exchange Online 사서함에 저장된 콘텐츠

사서함의 Exchange Online 메시지, 일정 항목, 작업 및 메모와 같은 전자 메일 관련 항목을 저장하는 데 주로 사용됩니다. 그러나 더 많은 클라우드 기반 앱이 사용자의 사서함에도 데이터를 저장함에 따라 변화하고 있습니다. 사서함에 데이터를 저장하면 콘텐츠 검색, Core eDiscovery 및 Advanced eDiscovery 도구를 사용하여 이러한 클라우드 기반 앱에서 데이터를 찾고 보고 내보낼 수 있습니다. 이러한 앱 중 일부의 데이터는 사서함의 비인간 메시지(비 IPM) 하위Tree에 있는 숨겨진 폴더에 저장됩니다. 다른 클라우드 기반 앱의 데이터는 사서함에 저장되지 않을 수  있지만 사서함과 연결되고 검색에 반환됩니다(해당 데이터가 검색 쿼리와 일치하는 경우).  클라우드 기반 데이터가 사용자 사서함에 저장되어 있는지 또는 사용자 사서함과 연결되어 있는지에 관계없이 일반적으로 사용자가 사서함을 열 때 해당 데이터는 전자 메일 클라이언트에 표시되지 않습니다.

다음 표에는 데이터를 저장하거나 클라우드 기반 사서함과 연결하는 앱이 나열됩니다. 또한 이 표에서는 각 앱에서 생성하는 콘텐츠 형식에 대해 설명합니다.

<br>

****

|Microsoft 365 앱|설명|
|---|---|
|양식<sup>*</sup>|양식 및 양식에 대한 응답은 전자 메일 메시지에 첨부되고 양식을 만든 사용자의 사서함에 있는 숨겨진 폴더에 저장되는 파일에 저장됩니다. 2020년 4월 전에 만든 양식은 PDF 파일로 저장됩니다. 2020년 이후에 만들어진 양식은 JSON 파일로 저장됩니다. 양식에 대한 응답은 CSV 파일에 저장됩니다. PST 파일의 Forms에서 콘텐츠를 내보낼 때 이 데이터는 **C9a559d2-7aab-4f13-a6ed-e7e9c52aec87과** 같이 이름이 지정되는 하위 폴더의 **ApplicationDataRoot** 폴더에 있습니다.|
|Microsoft 365 그룹|전자 메일 메시지, 일정 항목, 연락처(사용자), 메모 및 작업은 메일 그룹과 연결된 사서함에 Microsoft 365 저장됩니다.|
|Outlook/Exchange Online|전자 메일 메시지, 일정 항목, 연락처(사용자), 메모 및 작업은 사용자 사서함에 저장됩니다.|
|사용자|사용자 앱의 연락처(사용자 앱에서 액세스할 수 있는 연락처와 Outlook 연락처)는 사용자의 사서함에 저장됩니다.|
|클래스 일정|클래스 일정에서 만든 계획은 새 계획을 만들 때 프로비전되는 Microsoft 365 그룹의 사서함에 저장됩니다. 그룹 사서함의 별칭은 계획의 이름입니다.|
|비즈니스용 Skype|비즈니스용 Skype 대화는 사용자 사서함의 대화 기록 폴더에 저장됩니다. Skype 모임 참가자의 사서함에 소송 보존이 적용되거나 보존 정책에 할당된 경우 모임에 첨부된 파일은 참가자 사서함에 보존됩니다.|
|Sway<sup>*</sup>|Sways는 전자 메일 메시지에 첨부되고 sway를 만든 사용자의 사서함에 있는 숨겨진 폴더에 저장되는 HTML 파일로 저장됩니다. PST 파일에서 Sway에서 콘텐츠를 내보낼 때 이 데이터는 GUID가 **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba인** 하위 폴더의 **ApplicationDataRoot** 폴더에 있습니다.|
|Tasks|작업 앱의 작업(작업에서 액세스할 수 있는 작업과 Outlook)은 사용자의 사서함에 저장됩니다.|
|Teams|Teams 채널의 일부인 대화는 Teams 연결됩니다. *Teams(1 x N* 채팅이라고도 하는)의 채팅 목록에 있는 대화는 채팅에 참가하는 사용자의 사서함과 연결됩니다. 또한 Teams 채널의 모임 및 통화에 대한 요약 정보는 모임 또는 통화에 전화를 걸었다는 사용자의 사서함과 연결됩니다. 따라서 콘텐츠 Teams 검색할 때 채널 대화에서 Teams 검색하고 사용자 사서함에서 1 x N 채팅의 콘텐츠를 검색합니다.|
|할 일|To-Do 앱의 작업(할 일 목록에 저장되는 *to-dos)은* 사용자의 사서함에 저장됩니다.|
|Yammer|Yammer 커뮤니티 내의 대화 및 설명은 Microsoft 365 그룹 사서함, 만든 이의 사용자 사서함 및 명명된 받는 사람(@ 언급된 사용자 또는 Cc'ed 사용자)과 연결됩니다. Yammer 커뮤니티 외부로 전송된 개인 메시지는 개인 메시지에 참여하는 사용자의 사서함에 저장됩니다.|
|

> [!NOTE]
> <sup>*</sup>현재, (Core eDiscovery 또는 Advanced eDiscovery 사례에서 보류를 사용하여) 사서함에 보류가 배치된 경우 이 앱의 콘텐츠는 보류에 의해 보존되지 않습니다.
