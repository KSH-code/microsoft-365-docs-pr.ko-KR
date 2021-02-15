---
title: Exchange Online 사서함에 저장된 콘텐츠
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
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365의 클라우드 기반 앱에서 생성한 데이터는 사용자의 Exchange Online 사서함에 저장되거나 연결됩니다.
ms.openlocfilehash: f7bd5b00e8219f382078eb2d4f8aa25bd4c54d69
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750749"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>Exchange Online 사서함에 저장된 콘텐츠

Exchange Online의 사서함은 주로 메시지, 일정 항목, 작업 및 메모와 같은 전자 메일 관련 항목을 저장하는 데 사용됩니다. 그러나 클라우드 기반 앱이 사용자의 사서함에도 데이터를 저장함에 따라 이러한 변화가 있습니다. 사서함에 데이터를 저장하면 콘텐츠 검색, Core eDiscovery, Advanced eDiscovery의 검색 도구를 사용하여 이러한 클라우드 기반 앱에서 데이터를 찾고, 보고, 내보낼 수 있습니다. 이러한 앱 중 일부의 데이터는 사서함의 비 IPM(비 IPM) 하위 트러스트에 있는 숨겨진 폴더에 저장됩니다. 다른 클라우드 기반 앱의 데이터는 사서함에 저장되지 않을 수  있지만 사서함과 연결되고 검색에 반환됩니다(해당 데이터가 검색 쿼리와 일치하는 경우).  클라우드 기반 데이터가 사용자 사서함에 저장되어 있는지 또는 사용자 사서함과 연결되어 있는지에 관계없이 일반적으로 사용자가 사서함을 열 때 해당 데이터는 전자 메일 클라이언트에 표시되지 않습니다.

다음 표에는 데이터를 저장하거나 클라우드 기반 사서함과 연결하는 앱이 나열됩니다. 또한 이 표에는 각 앱이 생성하는 콘텐츠 형식도 설명됩니다.

|Microsoft 365 앱|설명|
|:---------|:---------|
|Forms|양식에 대한 양식 및 응답은 전자 메일 메시지에 첨부되고 양식을 만든 사용자의 사서함에 있는 숨겨진 폴더에 저장되는 파일에 저장됩니다. 2020년 4월 전에 만든 양식은 PDF 파일로 저장됩니다. 2020년 이후에 만들어진 양식은 JSON 파일로 저장됩니다.  양식에 대한 응답은 CSV 파일에 저장됩니다. PST 파일에서 Forms에서 콘텐츠를 내보낼 때 이 데이터는 **C9a559d2-7aab-4f13-a6ed-e7e9c52aec87로** 명명된 하위 폴더의 **ApplicationDataRoot** 폴더에 있습니다.|
|Microsoft 365 그룹|전자 메일 메시지, 일정 항목, 연락처(사용자), 메모 및 작업은 Microsoft 365 그룹과 연결된 사서함에 저장됩니다.|
|Outlook/Exchange Online|전자 메일 메시지, 일정 항목, 연락처(사용자), 메모 및 작업은 사용자의 사서함에 저장됩니다.|
|사용자|사용자 앱의 연락처(Outlook에서 액세스할 수 있는 연락처와 동일한 연락처)는 사용자의 사서함에 저장됩니다.|
|클래스 일정|클래스 일정에 만들어진 계획은 새 계획을 만들 때 프로비전되는 해당 Microsoft 365 그룹의 사서함에 저장됩니다. 그룹 사서함의 별칭은 계획의 이름입니다.|
|비즈니스용 Skype|비즈니스용 Skype의 대화는 사용자 사서함의 대화 기록 폴더에 저장됩니다. Skype 모임 참가자의 사서함에 소송 보존이 적용되거나 보존 정책에 할당된 경우 모임에 첨부된 파일은 참가자 사서함에 보존됩니다.|
|Sway|Sways는 전자 메일 메시지에 첨부되고 Sway를 만든 사용자의 사서함에 있는 숨겨진 폴더에 저장되는 HTML 파일로 저장됩니다. PST 파일에서 Sway에서 콘텐츠를 내보낼 때 이 데이터는 **ApplicationDataRoot** 폴더에 있습니다. **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba.**|
|작업|작업 앱의 작업(Outlook에서 액세스할 수 있는 작업과 동일한 작업)은 사용자의 사서함에 저장됩니다.|
|Teams|Teams 채널의 일부인 대화는 Teams 사서함과 연결됩니다. Teams의 채팅 *목록(1 x N* 채팅이라고도 하는)에 있는 대화는 채팅에 참여하는 사용자의 사서함과 연결됩니다. 또한 Teams 채널의 모임 및 통화에 대한 요약 정보는 모임 또는 통화에 전화를 걸고 있는 사용자의 사서함과 연결됩니다. 따라서 Teams 콘텐츠를 검색할 때 채널 대화에서 Teams 사서함에서 콘텐츠를 검색하고 사용자 사서함에서 1 x N 채팅의 콘텐츠를 검색합니다.| 
|To-Do|To-Do 앱의 작업(할 일 목록에 저장되는 *to-dos)은* 사용자의 사서함에 저장됩니다.|
|Yammer|Yammer 커뮤니티 내의 대화 및 설명은 Microsoft 365 그룹 사서함 및 만든 이의 사용자 사서함 및 명명된 받는 사람(@mentioned 또는 cc'ed 사용자)과 연결됩니다. Yammer 커뮤니티 외부로 전송된 개인 메시지는 비공개 메시지에 참여하는 사용자의 사서함에 저장됩니다.|  
||||

> [!NOTE]
> 현재 사서함에 보류가 설정되어 있는 경우(eDiscovery 및 Advanced eDiscovery 사례에서 보류 사용) Forms 및 Sway의 콘텐츠는 보류에 의해 보존되지 않습니다. 
