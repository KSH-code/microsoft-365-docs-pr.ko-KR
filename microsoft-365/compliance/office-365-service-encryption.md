---
title: 서비스 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '요약: 데이터 센터의 데이터 Microsoft Office 365.'
ms.openlocfilehash: b83b55afab2d9901e03a311d603b5b316531580a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60156465"
---
# <a name="service-encryption"></a>서비스 암호화

볼륨 수준 암호화를 사용하는 것 외에도 Exchange Online, Microsoft Teams, SharePoint Online 및 비즈니스용 OneDrive 암호화를 사용하여 고객 데이터를 암호화합니다. 서비스 암호화를 사용하면 다음과 같은 두 가지 주요 관리 옵션을 사용할 수 있습니다.

## <a name="microsoft-managed-keys"></a>Microsoft 관리 키
Microsoft는 서비스 암호화를 위한 루트 키를 포함하여 모든 암호화 키를 관리합니다. 이 옵션은 현재 온라인, Exchange Online, SharePoint 사용하도록 비즈니스용 OneDrive. 고객 키를 사용하여 온보드하기로 결정하지 않은 경우 Microsoft 관리 키는 기본 서비스 암호화를 제공합니다. 나중에 데이터 제거 경로를 따라가지 않고 고객 키 사용을 중지하면 Microsoft에서 관리하는 키를 사용하여 데이터가 암호화된 채로 유지됩니다. 데이터는 항상 이 기본 수준에서 암호화됩니다. 

## <a name="customer-key"></a>고객 키
서비스 암호화에 사용되는 루트 키를 제공하면 Azure Key Vault를 사용하여 이러한 키를 관리할 수 있습니다. Microsoft는 다른 모든 키를 관리합니다. 이 옵션을 고객 키라고 부르며 현재 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive. (이전에는 BYOK를 사용하여 고급 암호화라고 지칭했습니다. 원래 [공지 사항을 Office 365 투명성](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) 및 제어 강화를 참조합니다.)

서비스 암호화는 여러 가지 이점을 제공합니다.

- BitLocker 위에 추가된 보호 계층을 제공합니다.

- 운영 체제 관리자가 Windows 저장하거나 처리한 응용 프로그램 데이터에 액세스할 수 없습니다.

- 다중 테넌트 서비스가 테넌트당 키 관리를 제공할 수 있도록 하는 고객 키 옵션이 포함되어 있습니다.

- 암호화에 대한 특정 규정 Microsoft 365 요구 사항을 충족하는 고객의 요구 사항을 충족할 수 있는 기능을 향상합니다.

고객 키를 사용하면 HSM(On-premises Hardware Service Module) 또는 AKV(Azure Key Vault)를 사용하여 자체 암호화 키를 생성할 수 있습니다. 키를 생성하는 방법에 관계없이 AKV를 사용하여 키가 사용하는 암호화 키를 제어하고 Office 365. 키가 AKV에 저장되고 나면 사서함 데이터 또는 파일을 암호화하는 키 변경 중 하나의 루트로 사용할 수 있습니다.

고객 키의 또 다른 이점은 Microsoft가 데이터를 처리하는 기능을 제어할 수 있는 것입니다. Microsoft와의 Office 365 종료하거나 클라우드에 저장된 데이터의 일부를 제거하려는 경우와 같이 사용자 계정에서 데이터를 제거하려면 고객 키를 기술 컨트롤로 사용할 수 있습니다. 데이터를 제거하면 Microsoft를 비롯한 어느 누구도 데이터에 액세스하거나 데이터를 처리하지 않습니다. 고객 키는 Microsoft 직원이 데이터에 대한 액세스를 제어하는 데 사용하는 고객 Lockbox에 대한 추가 및 보완적입니다.

팀 사이트 및 온라인을 비롯한 Microsoft 365, Exchange Online, Microsoft Teams, SharePoint Online에 대한 고객 비즈니스용 OneDrive 설정하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [고객 키를 사용한 서비스 암호화](customer-key-overview.md)

- [고객 키 설정](customer-key-set-up.md)

- [고객 키 관리](customer-key-manage.md)

- [고객 키 또는 가용성 키 롤 또는 회전](customer-key-availability-key-roll.md)

- [가용성 키 이해](customer-key-availability-key-understand.md)
