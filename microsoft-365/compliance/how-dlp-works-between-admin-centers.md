---
title: Exchange 관리 센터에서 보안 및 & DLP가 작동하는 & 방법
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 보안 및 준수 & DLP가 Exchange 관리 센터의 DLP 및 메일 흐름 규칙(전송 규칙)에서 작동하는 방법을 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cd8a3eb0e7bb859ab9e10551fadd22cc7dcb2a39
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905940"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>보안 및 준수 센터와 Exchange 관리 센터 사이에서 DLP가 작동 하는 방식

Office 365에서는 두 개의 서로 다른 관리 센터에서 DLP(데이터 손실 방지) 정책을 만들 수 있습니다.
  
- 보안 **&** 준수 센터에서 단일 DLP 정책을 만들어 SharePoint, OneDrive, Exchange 및 이제 Microsoft Teams의 콘텐츠를 보호할 수 있습니다. 가능한 경우 여기에서 DLP 정책을 만드는 것이 좋습니다. 자세한 내용은 보안 및 준수 [센터의 DLP를 & 참조하세요.](data-loss-prevention-policies.md)
    
- Exchange **관리 센터에서** Exchange의 콘텐츠만 보호하는 데 도움이 되는 DLP 정책을 만들 수 있습니다. 이 정책은 Exchange 메일 흐름 규칙(전송 규칙)을 사용할 수 있으므로 전자 메일 처리와 관련한 더 많은 옵션이 있습니다. 자세한 내용은 Exchange 관리 [센터의 DLP를 참조하세요.](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
    
이러한 관리 센터에서 만든 DLP 경찰은 나란히 작동됩니다. 이 항목에서는 방법을 설명합니다.
  
![보안 및 준수 센터 및 Exchange 관리 센터의 DLP 페이지](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>보안 및 준수 & DLP가 Exchange 관리 센터의 DLP 및 메일 흐름 규칙과 작동하는 방식

보안 및 준수 센터에서 DLP 정책을 & 정책은 정책에 포함된 모든 위치에 배포됩니다. 정책에 Exchange Online이 포함되어 있는 경우 정책이 동기화된 후 Exchange 관리 센터에서 만든 DLP 정책과 정확히 동일한 방식으로 적용됩니다. 
  
Exchange 관리 센터에서 DLP 정책을 만든 경우 해당 정책은 보안 및 준수 센터에서 만든 전자 메일에 대한 모든 정책과 & 함께 사용할 수 있습니다. 그러나 Exchange 관리 센터에서 만든 규칙이 우선합니다. 모든 Exchange 메일 흐름 규칙이 먼저 처리된 다음 보안 및 준수 센터의 DLP & 처리됩니다.
  
즉,
  
- Exchange 메일 흐름 규칙에 의해 차단된 메시지는 보안 및 준수 센터에서 만든 DLP & 않습니다.
    
- Exchange 메일 흐름 규칙이 외부 사용자 추가와 같은 보안 및 준수 센터의 D & LP 정책과 일치하도록 하는 방식으로 메시지를 수정하는 경우 DLP 규칙은 이를 감지하고 필요한 경우 정책을 적용합니다.
    
또한 "처리 중지" 작업을 사용하는 Exchange 메일 흐름 규칙은 보안 및 준수 센터에서 DLP 규칙 & 영향을 주지 않습니다. 이러한 규칙은 계속 처리됩니다.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>보안 및 준수 & 및 Exchange 관리 센터의 정책 팁

정책 팁은 Exchange 관리 센터에서 만든 DLP 정책 및 메일 흐름 규칙 또는 보안 및 준수 센터에서 만든 DLP & 사용할 수 있지만 둘 다 사용할 수 없습니다. 이러한 정책은 서로 다른 위치에 저장되지만 정책 팁은 단일 위치에서만 그릴 수 있기 때문에입니다.
  
Exchange 관리 센터에서 정책 팁을 구성한 경우 Exchange 관리 센터에서 팁을 해제할 때까지 보안 & 준수 센터에서 구성한 정책 팁은 웹용 Outlook 및 Outlook 2013 이상에서 사용자에게 나타나지 않습니다. 이렇게 하면 보안 및 준수 센터로 전환하도록 선택할 때까지 현재 Exchange 메일 흐름 규칙이 & 있습니다.
  
정책 팁은 단일 위치에서만 그릴 수 있는 반면, 보안 및 준수 센터와 Exchange 관리 센터 둘 다에서 DLP 정책을 사용하는 경우에도 항상 전자 메일 & 전송됩니다.
