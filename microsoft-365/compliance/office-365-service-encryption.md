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
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '요약: Microsoft Office 365의 데이터 복구 기능을 이해 합니다.'
ms.openlocfilehash: ec7f794a62a910fadaece890cf73451644d44109
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071115"
---
# <a name="office-365-service-encryption"></a>Office 365 서비스 암호화

볼륨 수준 암호화, Exchange Online, 비즈니스용 Skype, SharePoint Online 및 비즈니스용 OneDrive를 사용 하는 것 외에도 서비스 암호화를 사용 하 여 고객 데이터를 암호화 합니다. 서비스 암호화를 사용 하면 다음과 같은 두 가지 주요 관리 옵션을 사용할 수 있습니다.

- Microsoft는 모든 암호화 키를 관리 합니다. (이 옵션은 현재 SharePoint Online, 비즈니스용 OneDrive 및 비즈니스용 Skype에서 사용할 수 있습니다.)

- 고객은 서비스 암호화에 사용 되는 루트 키를 제공 하며, 고객은 Azure Key Vault를 사용 하 여 이러한 키를 관리 합니다. Microsoft는 다른 모든 키를 관리 합니다. 이 옵션은 고객 키 라고 하며, 현재 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive에 사용할 수 있습니다. 이전에는 고급 암호화 라고 합니다. 원래 공지 사항을 보려면 [Office 365 고객을 위해 투명도 및 컨트롤 향상](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) 을 참조 하세요.

서비스 암호화는 여러 가지 이점을 제공 합니다. 예를 들면 고객 키:

- 강력한 암호화 보호에 대 한 권한 보호 및 관리 기능을 제공 합니다.

- 다중 테 넌 트 서비스가 테 넌 트 기준 키 관리를 제공할 수 있도록 하는 고객 키 옵션이 포함 됩니다.

- Windows 운영 체제 관리자가 운영 체제에 의해 저장 되거나 처리 되는 고객 데이터에 대 한 액세스와의 분리를 제공 합니다.

- 암호화에 대 한 준수 요구 사항이 있는 고객의 요구 사항을 충족 하기 위해 Office 365의 기능을 향상 시킵니다.

## <a name="customer-key"></a>고객 키

고객 키를 사용 하 여 온-프레미스 HSM (하드웨어 서비스 모듈) 또는 AKV (Azure Key Vault)를 사용 하 여 자체 암호화 키를 생성할 수 있습니다. 키를 생성 하는 방법에 관계 없이 AKV을 사용 하 여 Office 365에서 사용 하는 암호화 키를 제어 하 고 관리 합니다. 키가 AKV에 저장 되 면 사서함 데이터 나 파일을 암호화 하는 keychains 중 하나의 루트로 사용할 수 있습니다.

고객 키의 또 다른 이점은 Microsoft에서 데이터를 처리 하는 기능을 제어 하는 것입니다. Microsoft에 대 한 서비스를 종료 하거나 클라우드에 저장 된 데이터 부분을 제거 하려는 경우와 같이 Office 365에서 데이터를 제거 하려는 경우에는이 작업을 수행 하 고 고객 키를 기술 컨트롤로 사용할 수 있습니다. 이렇게 하면 Microsoft를 비롯 한 아무도 데이터에 액세스 하거나 처리할 수 없습니다. 고객 키는 Microsoft 담당자가 데이터에 대 한 액세스를 제어 하는 데 사용 하는 고객 Lockbox와 보조로 추가 됩니다.

Exchange Online, 비즈니스용 Skype, SharePoint Online (팀 사이트 포함) 및 비즈니스용 OneDrive에 대해 Office 365에 대 한 고객 키를 설정 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [Office 365의 고객 키를 사용한 서비스 암호화](customer-key-overview.md)

- [Office 365에 대 한 고객 키 설정](customer-key-set-up.md)

- [Office 365에 대 한 고객 키 관리](customer-key-manage.md)

- [고객 키 또는 가용성 키 롤 또는 회전](customer-key-availability-key-roll.md)

- [가용성 키 이해](customer-key-availability-key-understand.md)
 
