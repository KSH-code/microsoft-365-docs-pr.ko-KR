---
title: Office 365 서비스 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '요약: Microsoft Office 365의 서비스 계층에서 데이터 암호화를 이해 합니다.'
ms.openlocfilehash: fb6bf87fbd51bcb4383e9eb595ef11f081989d86
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211945"
---
# <a name="office-365-service-encryption"></a>Office 365 서비스 암호화

볼륨 수준 암호화를 위해 BitLocker를 사용 하는 것 외에도 Exchange Online, 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive 및 팀은 서비스 암호화를 사용 하 여 고객 데이터를 암호화 합니다. 서비스 암호화를 사용 하면 다음과 같은 두 가지 주요 관리 옵션을 사용할 수 있습니다.

- Microsoft는 모든 암호화 키를 관리 합니다. 이 옵션은 현재 SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype 및 팀 채팅에서 사용할 수 있습니다. 데이터는 기본적으로 Microsoft 관리 키를 사용 하 여 암호화 됩니다.

- 조직에서 루트 키를 제공 합니다. Azure 키 자격 증명 모음을 사용 하 여 이러한 키를 관리 합니다. 이 옵션을 Customer 키 라고 합니다. 현재 Exchange Online, SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype 및 팀 파일에 대해 고객 키를 사용할 수 있습니다. 고객 키를 사용 하는 경우 이러한 키는 Microsoft 관리 되는 키를 대체 하 여 데이터를 암호화 합니다.

어떤 옵션을 선택 하든지 서비스 암호화는 여러 가지 이점을 제공 합니다.

- 사용자 인증을 적용 하 여 권한 있는 사용자가 요청한 데이터를 검색 하 고 해독 합니다.

- Windows 운영 체제 관리자가 운영 체제에 의해 저장 되거나 처리 되는 고객 데이터에 대 한 액세스와의 분리를 제공 합니다.

- 암호화에 대 한 준수 요구 사항이 있는 고객의 요구 사항을 충족 하기 위해 Office 365의 기능을 향상 시킵니다.

Exchange Online, 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 Office 365의 고객 키를 설정 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [Office 365의 고객 키를 사용한 서비스 암호화](customer-key-overview.md)

- [Office 365에 대 한 고객 키 설정](customer-key-set-up.md)

- [Office 365에 대 한 고객 키 관리](customer-key-manage.md)

- [고객 키 또는 가용성 키 롤 또는 회전](customer-key-availability-key-roll.md)

- [가용성 키 이해](customer-key-availability-key-understand.md)
