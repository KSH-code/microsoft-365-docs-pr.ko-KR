---
title: Office 365의 고객 키를 사용한 서비스 암호화
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 고객 키를 사용 하 여 조직의 암호화 키를 제어 하 고 Office 365을 구성 하 여 Microsoft의 데이터 센터에 있는 휴지 상태에 있는 사용자에 대 한 정보를 암호화 합니다.
ms.openlocfilehash: 6fd7167dd46f3a44d97a493830aef19e40f062e8
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076931"
---
# <a name="service-encryption-with-customer-key-in-office-365"></a>Office 365의 고객 키를 사용한 서비스 암호화

Office 365은 BitLocker 및 DKM (분산 키 관리자)를 통해 사용 하도록 설정 된 기준선, 볼륨 수준의 암호화를 제공 합니다. Office 365에서는 콘텐츠의 응용 프로그램 수준에 추가 된 암호화 계층을 제공 합니다. 이 콘텐츠에는 Exchange Online, 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive 및 팀 파일의 데이터가 포함 됩니다. 이 추가 된 암호화 계층을 서비스 암호화 라고 합니다.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>서비스 암호화, BitLocker 및 고객 키가 함께 작동 하는 방식

서비스 암호화는 rest의 콘텐츠가 응용 프로그램 계층에서 암호화 되도록 합니다. **데이터는 항상 BitLocker 및 DKM를 사용 하는 Office 365 서비스의 나머지 부분에서 암호화 됩니다**. 자세한 내용은 "Office 365의 보안, 개인 정보 및 준수 정보" 및 [Exchange Online에서 전자 메일 암호를 보호 하는 방법을](exchange-online-secures-email-secrets.md)참조 하세요. 고객 키는 무단 시스템 또는 담당자의 데이터 보기를 방지 하 고, Microsoft 데이터 센터에서 BitLocker 디스크 암호화를 보완 합니다. 서비스 암호화는 Microsoft 직원이 고객 데이터에 액세스 하지 못하도록 하기 위한 것이 아닙니다. 기본 목적은 고객에 게 루트 키 제어를 위한 규정 준수 의무를 지원 하기 위한 것입니다. 고객은 해당 암호화 키를 사용 하 여 eDiscovery, 맬웨어 방지, 스팸 방지, 검색 인덱싱 등과 같은 부가 가치 클라우드 서비스를 제공 하도록 O365 서비스에 명시적으로 권한을 부여 합니다.

고객 키는 서비스 암호화를 기반으로 구축 되며 암호화 키를 제공 하 고 제어할 수 있습니다. 그러면 Office 365에서 이러한 키를 사용 하 여 [OST (온라인 서비스 약관)](https://www.microsoft.com/licensing/product-licensing/products.aspx)에 설명 된 대로 휴지 상태의 데이터를 암호화 합니다. 고객 키는 Office 365에서 데이터를 암호화 하 고 암호를 해독 하는 데 사용 하는 암호화 키를 제어 하므로 준수 의무를 달성 하는 데 도움이 됩니다.
  
고객 키를 사용 하면 클라우드 서비스 공급자와의 키 배치를 지정 하는 규정 준수 요구 사항을 충족 하는 조직의 기능을 향상 시킬 수 있습니다. 고객 키를 사용 하 여 응용 프로그램 수준에서 Office 365 데이터에 대 한 루트 암호화 키를 제공 하 고 제어할 수 있습니다. 따라서 조직의 키를 제어할 수 있습니다. 서비스를 종료 하기로 결정 하면 조직의 루트 키에 대 한 액세스 권한을 해지할 수 있습니다. 모든 Office 365 서비스에 대해 키에 대 한 액세스를 취소 하는 것은 데이터 삭제에 대 한 경로의 첫 단계입니다. 키에 대 한 액세스를 취소 하면 서비스에서 데이터를 읽을 수 없게 됩니다.

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>고객 키가 Office 365에서 휴지 데이터를 암호화 합니다.

사용자가 제공한 키를 사용 하 여 Office 365의 고객 키를 암호화 합니다.

- SharePoint Online, 비즈니스용 OneDrive 및 팀 파일
- 비즈니스용 OneDrive에 업로드 된 파일
- 전자 메일 본문 콘텐츠, 일정 항목 및 전자 메일 첨부 파일 내의 콘텐츠를 포함 하는 Exchange Online 사서함 콘텐츠
- 비즈니스용 Skype의 텍스트 대화입니다.

현재는 Skype 모임 브로드캐스트 및 Skype 모임 콘텐츠 업로드에 대 한 암호화 키에 대 한 고객 제어를 제공 하지 않습니다. 대신이 콘텐츠는 Office 365의 다른 모든 콘텐츠와 함께 암호화 됩니다.

### <a name="customer-key-with-hybrid-deployments"></a>하이브리드 배포를 포함 하는 고객 키

고객 키는 클라우드의 휴지 부분에 있는 데이터만 암호화 합니다. 고객 키가 온-프레미스 사서함과 파일을 보호 하는 데 작동 하지 않습니다. BitLocker와 같은 다른 방법을 사용 하 여 온-프레미스 데이터를 암호화할 수 있습니다.

## <a name="about-the-data-encryption-policy-dep"></a>DEP (데이터 암호화 정책) 정보

데이터 암호화 정책은 사용자가 제공한 각 키와 Microsoft에서 보호 하는 가용성 키를 사용 하 여 데이터를 암호화 하는 암호화 계층 구조를 정의 합니다. 각 서비스 마다 다른 PowerShell cmdlet을 사용 하 여 DEPs를 만들고 응용 프로그램 데이터를 암호화 하는 것을 할당 합니다. 예:

**Exchange Online 및 비즈니스용 Skype** 테 넌 트 당 최대 50 DEPs를 만들 수 있습니다. DEPs를 Azure 키 자격 증명 모음의 고객 키에 연결한 다음 개별 사서함에 DEPs를 할당 합니다. 사서함에 DEP를 할당 하는 경우 다음을 수행 합니다.

- 사서함이 사서함 이동으로 표시 되어 있습니다. 여기에 설명 된 대로 Office 365의 우선 순위에 따라 [office 365 서비스의 이동 요청](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)을 사용 합니다.

- 사서함이 이동 되는 동안 암호화가 수행 됩니다. 사서함에 대 한 72 시간을 새 DEP로 암호화할 수 있도록 허용 합니다. DEP를 지정한 시간부터 72 시간을 기다린 후 사서함이 암호화 되지 않은 경우 Microsoft에 문의 하십시오.

나중에 DEP를 새로 고치거 나 [Office 용 고객 키 관리 365](customer-key-manage.md)에 설명 된 것 처럼 다른 dep를 사서함에 할당할 수 있습니다. DEP를 할당 하려면 각 사서함에 적절 한 라이선스가 있어야 합니다. 라이선스에 대 한 자세한 내용은 [Customer 키를 설정 하기 전에](customer-key-set-up.md#before-you-set-up-customer-key)를 참조 하세요.

**SharePoint Online, 비즈니스용 OneDrive 및 팀 파일** 다중 지역 기능을 사용 하는 경우 조직에 대 한 geo 당 최대 하나의 DEP를 만들 수 있습니다. 각 지역에 대해 서로 다른 고객 키를 사용할 수 있습니다. 다중 지역 기능을 사용 하지 않는 경우에는 테 넌 트 당 하나의 DEP만 만들 수 있습니다. DEP를 할당 하면 암호화가 자동으로 시작 되지만 완료 하는 데 시간이 걸릴 수 있습니다. [Office 365에 대 한 고객 키 설정](customer-key-set-up.md)의 세부 정보를 참조 하세요.

## <a name="leaving-the-service"></a>서비스 종료

고객 키는 Office 365 서비스에서 나갈 때 키를 해지할 수 있도록 하 여 준수 의무를 지 원하는 데 도움을 줍니다. 서비스를 종료 하는 과정에서 키를 해지 하면 가용성 키가 삭제 되어 데이터의 암호화가 삭제 됩니다. 암호화 삭제는 보안 및 준수 의무를 충족 하는 데 중요 한 데이터를 다시 작성 하는 위험을 완화 합니다. 데이터 제거 프로세스 및 키 해지에 대 한 자세한 내용은 [키 해지 및 데이터 제거 경로 프로세스 시작](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)을 참조 하십시오.

### <a name="encryption-ciphers-used-by-customer-key"></a>고객 키에 사용 되는 암호화 암호

고객 키는 다양 한 암호화 암호를 사용 하 여 다음 그림에 표시 된 대로 키를 암호화 합니다.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype에 대 한 키를 암호화 하는 데 사용 되는 암호화 암호

![Exchange Online 고객 키에 대 한 암호화 암호](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 키를 암호화 하는 데 사용 되는 암호화 암호

![SharePoint Online 고객 키에 대 한 암호화 암호](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>관련 문서

- [Office 365에 대 한 고객 키 설정](customer-key-set-up.md)

- [Office 365에 대 한 고객 키 관리](customer-key-manage.md)

- [고객 키 또는 가용성 키 롤 또는 회전](customer-key-availability-key-roll.md)

- [가용성 키에 대 한 자세한 정보](customer-key-availability-key-understand.md)

- [Office 365의 고객 Lockbox](customer-lockbox-requests.md)

- [Office 365 서비스 암호화](office-365-service-encryption.md)
