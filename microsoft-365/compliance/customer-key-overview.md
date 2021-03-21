---
title: 고객 키를 사용한 서비스 암호화
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
- m365solution-mip
- m365initiative-compliance
ms.custom: seo-marvel-apr2020
description: 이 문서에서는 서비스 암호화가 Microsoft 365의 고객 키와 함께 작동하는 방식에 대해 배우게 됩니다.
ms.openlocfilehash: 9ed4b523c77cf1fa80d23e8fbe5c93e938f222a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916890"
---
# <a name="service-encryption-with-customer-key"></a>고객 키를 사용한 서비스 암호화

Microsoft 365는 BitLocker 및 DKM(분산 키 관리자)을 통해 활성화된 기본 볼륨 수준 암호화를 제공합니다. Microsoft 365는 콘텐츠의 응용 프로그램 계층에서 추가된 암호화 계층을 제공합니다. 이 콘텐츠에는 Exchange Online, 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 데이터가 포함됩니다. 이러한 추가된 암호화 계층을 서비스 암호화라고 합니다.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>서비스 암호화, BitLocker 및 고객 키가 함께 작동 하는 방법

서비스 암호화를 사용하면 미사용 콘텐츠가 서비스 계층에서 암호화됩니다. **데이터는 BitLocker 및 DKM을 사용하여 Microsoft 365** 서비스에서 항상 미사일 시 암호화됩니다. 자세한 내용은 "보안, 개인 정보 보호 및 규정 준수 정보" 및 Exchange Online에서 전자 메일 비밀을 보호하는 [방법을 참조하세요.](exchange-online-secures-email-secrets.md) 고객 키는 권한이 없는 시스템이나 직원의 데이터를 볼 수 있도록 추가 보호 기능을 제공하며 Microsoft 데이터 센터에서 BitLocker 디스크 암호화를 보완합니다. 서비스 암호화는 Microsoft 직원이 고객 데이터에 액세스하지 못하게 하는 데 사용되지 않습니다. 기본 목적은 고객이 루트 키를 제어하기 위한 규정 또는 준수 의무를 충족하도록 지원하기 위한 것입니다. 고객은 O365 서비스에 암호화 키를 사용하여 eDiscovery, 맬웨어 방지, 스팸 방지, 검색 인덱싱 등의 부가 가치 클라우드 서비스를 제공할 수 있도록 명시적으로 권한을 가합니다.

고객 키는 서비스 암호화를 바탕으로 구축되어 암호화 키를 제공하고 제어할 수 있습니다. 그런 다음 Microsoft 365는 이러한 키를 사용하여 [OST(온라인](https://www.microsoft.com/licensing/product-licensing/products.aspx)서비스 약관)에 설명된 바와 같이 미사용 데이터를 암호화합니다. 고객 키는 Microsoft 365에서 데이터를 암호화하고 암호 해독하는 데 사용하는 암호화 키를 제어하기 때문에 규정 준수 의무를 충족하는 데 도움이 됩니다.
  
고객 키는 클라우드 서비스 공급자와의 주요 계약을 지정하는 규정 준수 요구 사항의 요구 사항을 충족하는 조직의 기능을 향상합니다. 고객 키를 사용하여 응용 프로그램 수준에서 미사용 Microsoft 365 데이터에 대한 루트 암호화 키를 제공하고 제어합니다. 따라서 조직의 키를 제어할 수 있습니다. 서비스를 종료하기로 결정한 경우 조직의 루트 키에 대한 액세스를 해지합니다. 모든 Microsoft 365 서비스의 경우 키에 대한 액세스를 해지하는 것은 데이터 지우기 경로의 첫 번째 단계입니다. 키에 대한 액세스를 해지하면 데이터를 서비스에 읽을 수 없습니다.

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>고객 키는 Office 365에서 휴지의 데이터를 암호화합니다.

제공한 키를 사용하여 고객 키는 다음을 암호화합니다.

- SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일.
- 비즈니스용 OneDrive에 업로드된 파일.
- 전자 메일 본문 콘텐츠, 일정 항목 및 전자 메일 첨부 파일 내의 콘텐츠를 포함한 Exchange Online 사서함 콘텐츠
- 비즈니스용 Skype에서 텍스트 대화.

현재 Skype 모임 브로드캐스트 및 Skype 모임 콘텐츠 업로드에 대한 암호화 키에 대한 고객 제어는 제공되지 않습니다. 대신 이 콘텐츠는 Office 365의 다른 모든 콘텐츠와 함께 암호화됩니다.

### <a name="customer-key-with-hybrid-deployments"></a>하이브리드 배포가 있는 고객 키

고객 키는 클라우드에서 휴지의 데이터만 암호화합니다. 고객 키는 프레미스 사서함 및 파일을 보호하기 위해 작동하지 않습니다. BitLocker와 같은 다른 방법을 사용하여 사내 데이터를 암호화할 수 있습니다.

## <a name="about-the-data-encryption-policy-dep"></a>DEP(데이터 암호화 정책) 정보

데이터 암호화 정책은 사용자가 제공하는 각 키와 Microsoft에서 보호하는 가용성 키를 사용하여 데이터를 암호화하는 암호화 계층 구조를 정의합니다. 서비스마다 다른 PowerShell cmdlet을 사용하여 DEP를 만들고 이러한 DEP를 할당하여 응용 프로그램 데이터를 암호화합니다. 예를 들어 다음과 같습니다.

**Exchange Online 및 비즈니스용 Skype** 테넌트당 최대 50 DEP를 만들 수 있습니다. AZURE Key Vault의 고객 키에 DEP를 연결한 다음 DEP를 개별 사서함에 할당합니다. 사서함에 DEP를 할당하는 경우:

- 사서함이 사서함 이동으로 표시됩니다. 여기에 설명된 Microsoft 365의 우선 순위에 따라 [Microsoft 365 서비스에서](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)요청 이동 .

- 사서함을 이동하는 동안 암호화가 진행됩니다. 새 DEP를 사용하여 사서함을 암호화하는 데 72시간을 허용합니다. DEP를 할당한 시간부터 72시간을 기다렸다가 사서함이 암호화되지 않은 경우 Microsoft에 문의합니다.

나중에 [Manage Customer Key for Office 365에](customer-key-manage.md)설명된 바와 같이 DEP를 새로 고치거나 사서함에 다른 DEP를 할당할 수 있습니다. DEP를 할당하려면 각 사서함에 적절한 라이선스가 있어야 합니다. 라이선스에 대한 자세한 내용은 고객 키를 [설정하기 전에를 참조하세요.](customer-key-set-up.md#before-you-set-up-customer-key)

> [!NOTE]
> 이러한 사서함 유형 중 일부는 할당된 라이선스(공용 폴더 사서함 및 Microsoft 365 그룹 사서함)일 수 없는 경우나 저장소 증가를 위한 라이선스(공유 사서함)가 필요한 경우에도 사용자 사서함에 대한 라이선스 요구 사항을 충족하는 테넌트에 대해 공유 사서함, 공용 폴더 사서함 및 Microsoft 365 그룹 사서함에 DEP를 적용할 수 있습니다.

**SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일** Multi-Geo 기능을 사용하는 경우 조직에 대해 지리적으로 최대 하나의 DEP를 만들 수 있습니다. 각 지리적으로 서로 다른 고객 키를 사용할 수 있습니다. Multi-Geo 기능을 사용하지 않는 경우 테넌트당 DEP를 하나만 만들 수 있습니다. DEP를 할당하면 암호화가 자동으로 시작되지만 완료하는 데 시간이 걸릴 수 있습니다. 고객 키 설정 [의 세부 정보를 참조합니다.](customer-key-set-up.md)

## <a name="leaving-the-service"></a>서비스 종료

고객 키는 Microsoft 365 서비스를 떠날 때 키를 해지할 수 있도록 하여 규정 준수 의무를 충족하도록 도와드립니다. 서비스를 종료할 때 키를 해지하면 가용성 키가 삭제되어 데이터가 암호화에서 삭제됩니다. 암호화를 해제하면 보안 및 규정 준수 의무를 충족하는 데 중요한 데이터 다시 사용 위험을 완화할 수 있습니다. 데이터 제거 프로세스 및 키 해지에 대한 자세한 내용은 키 해지 및 데이터 제거 경로 프로세스 시작을 [참조하세요.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

### <a name="encryption-ciphers-used-by-customer-key"></a>고객 키에서 사용하는 암호화 암호화

고객 키는 다음 그림과 같이 다양한 암호화 암호화를 사용하여 키를 암호화합니다.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype의 키를 암호화하는 데 사용되는 암호화 암호

![Exchange Online 고객 키 암호화](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 키를 암호화하는 데 사용되는 암호화 암호

![SharePoint Online 고객 키의 암호화 암호화](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>관련 문서

- [고객 키 설정](customer-key-set-up.md)

- [고객 키 관리](customer-key-manage.md)

- [고객 키 또는 가용성 키 롤 또는 회전](customer-key-availability-key-roll.md)

- [가용성 키에 대해 자세히 알아보기](customer-key-availability-key-understand.md)

- [고객 Lockbox](customer-lockbox-requests.md)

- [서비스 암호화](office-365-service-encryption.md)