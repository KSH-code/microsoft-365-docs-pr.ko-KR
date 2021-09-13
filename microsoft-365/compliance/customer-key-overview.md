---
title: 고객 키를 사용한 서비스 암호화
ms.author: krowley
author: kccross
manager: laurawi
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
description: 이 문서에서는 서비스 암호화가 고객 키와 함께 작동하는 방식에 대해 Microsoft 365.
ms.openlocfilehash: 7f765d8a9c59ad8bdc5e7d2edba7f18af426cc76
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216882"
---
# <a name="service-encryption-with-customer-key"></a>고객 키를 사용한 서비스 암호화

Microsoft 365 BitLocker 및 DKM(분산 키 관리자)을 통해 사용하도록 설정된 기준 볼륨 수준 암호화를 제공합니다. Microsoft 365 콘텐츠에 대해 추가 암호화 계층을 제공합니다. 이 콘텐츠에는 Exchange Online, 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>서비스 암호화, BitLocker 및 고객 키가 함께 작동 하는 방법

데이터는 항상 BitLocker 및 DKM을 사용하여 Microsoft 365 암호화됩니다. 자세한 내용은 전자 메일 Exchange Online [보호하는 방법을 참조하세요.](exchange-online-secures-email-secrets.md) 고객 키는 권한이 없는 시스템이나 직원이 데이터를 볼 수 있도록 추가 보호를 제공하며 Microsoft 데이터 센터에서 BitLocker 디스크 암호화를 보완합니다. 서비스 암호화는 Microsoft 직원이 데이터에 액세스하지 못하게 하는 데 사용되지 않습니다. 대신 고객 키는 루트 키를 제어하기 위한 규정 또는 준수 의무를 충족하는 데 도움이 됩니다. 암호화 Microsoft 365 사용하여 eDiscovery, 맬웨어 방지, 스팸 방지, 검색 인덱싱 등의 부가 가치 클라우드 서비스를 제공하기 위해 암호화 키를 사용할 수 있는 권한을 명시적으로 승인합니다.

고객 키는 서비스 암호화를 바탕으로 구축되어 암호화 키를 제공하고 제어할 수 있습니다. Microsoft 365 [OST(온라인](https://www.microsoft.com/licensing/product-licensing/products.aspx)서비스 약관)에 설명된 바와 같이 이러한 키를 사용하여 미사용 데이터를 암호화합니다. 고객 키는 데이터 암호화 및 암호 해독에 사용하는 암호화 키를 Microsoft 365 준수 의무를 충족하는 데 도움이 됩니다.
  
고객 키는 클라우드 서비스 공급자와의 주요 계약을 지정하는 규정 준수 요구 사항의 요구 사항을 충족하는 조직의 기능을 향상합니다. 고객 키를 사용하여 응용 프로그램 수준에서 미사용 데이터에 대한 Microsoft 365 암호화 키를 제공하고 제어합니다. 따라서 조직의 키를 제어할 수 있습니다.

## <a name="customer-key-with-hybrid-deployments"></a>하이브리드 배포가 있는 고객 키

고객 키는 클라우드에서 휴지의 데이터만 암호화합니다. 고객 키는 프레미스 사서함 및 파일을 보호하기 위해 작동하지 않습니다. BitLocker와 같은 다른 방법을 사용하여 사내 데이터를 암호화할 수 있습니다.

## <a name="about-data-encryption-policies"></a>데이터 암호화 정책 정보

DEP(데이터 암호화 정책)는 암호화 계층 구조를 정의합니다. 이 계층 구조는 사용자가 관리하는 각 키와 Microsoft에서 보호하는 가용성 키를 사용하여 데이터를 암호화하는 데 사용됩니다. PowerShell cmdlet을 사용하여 DEP를 만든 다음 해당 DEP를 할당하여 응용 프로그램 데이터를 암호화합니다. 고객 키에 의해 지원되는 DEP에는 Microsoft 365 있으며, 각 정책 유형은 서로 다른 cmdlet을 사용하며 서로 다른 유형의 데이터에 대한 범위를 제공합니다. 정의할 수 있는 DEP는 다음과 같습니다.

**여러 작업 부하에 Microsoft 365 DEP** 이러한 DEP는 테넌트 내의 모든 사용자에 대해 여러 M365 작업에서 데이터를 암호화합니다. 이러한 워크로드에는 다음이 포함됩니다.

- Teams 채팅 메시지(1:1 채팅, 그룹 채팅, 모임 채팅 및 채널 대화)
- Teams 미디어 메시지(이미지, 코드, 비디오 메시지, 오디오 메시지, Wiki 이미지)
- Teams 저장소에 저장된 통화 및 모임 Teams 기록
- Teams 알림
- Teams 채팅 제안을 Cortana
- Teams 메시지 표시
- 사용자 및 사용자에 대한 Exchange Online
- Exchange Online DEP에 의해 암호화되지 않은 사서함
- Microsoft Information Protection:

  - 데이터 파일 스키마, 규칙 패키지 및 중요한 데이터를 해시하는 데 사용되는 솔트 등의 정확한 데이터 일치(EDM) 데이터 EDM 및 Microsoft Teams 경우 다중 작업 DEP는 DEP를 테넌트에 할당한 시간부터 새 데이터를 암호화합니다. 고객 Exchange Online 위해 고객 키는 모든 기존 및 새 데이터를 암호화합니다.

  - 민감도 레이블에 대한 레이블 구성

다중 작업 DEP는 다음과 같은 유형의 데이터를 암호화하지 않습니다. 대신 Microsoft 365 다른 유형의 암호화를 사용하여 이 데이터를 보호할 수 있습니다.

- SharePoint 비즈니스용 OneDrive 데이터를 저장합니다.
- Microsoft Teams 및 Teams 및 SharePoint 비즈니스용 OneDrive Online에 저장된 일부 통화 및 모임 녹음/녹화는 SharePoint 온라인 DEP를 사용하여 암호화됩니다.
- 고객 Microsoft 365 지원되지 않는 Yammer 및 Planner와 같은 기타 작업 부하
- Teams 라이브 이벤트 데이터입니다.

테넌트당 여러 DEP를 만들 수 있지만 한 때 하나의 DEP만 할당할 수 있습니다. DEP를 할당하면 암호화가 자동으로 시작되지만 테넌트의 크기에 따라 완료하는 데 시간이 다소 걸립니다.

**사서함의 EXCHANGE ONLINE DEP** 사서함 DEP는 사서함 내의 개별 사서함을 보다 Exchange Online. 사서함 DEP를 사용하여 UserMailbox, MailUser, Group, PublicFolder 및 Shared 사서함과 같은 여러 유형의 EXO 사서함에 저장된 데이터를 암호화합니다. 테넌트당 최대 50개 활성 DEP를 사용할 수 있으며 이러한 DEP를 개별 사서함에 할당할 수 있습니다. 하나의 DEP를 여러 사서함에 할당할 수 있습니다.

기본적으로 사서함은 Microsoft 관리 키를 사용하여 암호화됩니다. 사서함에 고객 키 DEP를 할당하는 경우:

- 사서함이 다중 작업 DEP를 사용하여 암호화된 경우 서비스에서는 사용자 또는 시스템 작업이 사서함 데이터에 액세스하는 한 새 사서함 DEP를 사용하여 사서함을 다시 그렸다.

- 사서함이 Microsoft 관리 키를 사용하여 이미 암호화된 경우 서비스에서는 사용자 또는 시스템 작업이 사서함 데이터에 액세스하는 한 새 사서함 DEP를 사용하여 사서함을 다시 그렸다.

- 기본 암호화를 사용하여 사서함을 아직 암호화하지 않은 경우 서비스에서 이동을 위해 사서함을 표시합니다. 이동이 완료되면 암호화가 진행됩니다. 사서함 이동은 모든 사서함에 대해 설정된 우선 순위에 따라 Microsoft 365. 자세한 내용은 Move [requests in the Microsoft 365 참조하세요.](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-microsoft-365-or-office-365-service) 사서함이 지정된 시간 내에 암호화되지 않은 경우 Microsoft에 문의하십시오.

나중에 에 대한 고객 키 관리에 설명된 바와 같이 DEP를 새로 고치거나 사서함에 다른 DEP를 [할당할 Office 365.](customer-key-manage.md) 각 사서함에는 DEP를 할당할 적절한 라이선스가 있어야 합니다. 라이선스에 대한 자세한 내용은 고객 키를 [설정하기 전에를 참조하세요.](customer-key-set-up.md#before-you-set-up-customer-key)

DEP는 사용자 사서함에 대한 라이선스 요구 사항을 충족하는 테넌트에 대해 공유 사서함Microsoft 365 공용 폴더 사서함 및 그룹 사서함에 할당할 수 있습니다. 고객 키 DEP를 할당하기 위해 사용자별 사서함이 아닌 사서함에 대해 별도의 라이선스가 필요하지 않습니다.

개별 사서함에 할당하는 고객 키 DEP의 경우 서비스를 떠날 때 Microsoft에서 특정 DEP를 제거하도록 요청할 수 있습니다. 데이터 제거 프로세스 및 키 해지에 대한 자세한 내용은 키 해지 및 데이터 제거 경로 프로세스 시작을 [참조하세요.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

서비스 종료의 일부로 키에 대한 액세스를 해지하면 가용성 키가 삭제되어 데이터가 암호화에서 삭제됩니다. 암호화를 해제하면 데이터 다시 사용 위험이 완화됩니다. 이는 보안 및 규정 준수 의무를 충족하는 데 중요합니다.

**SharePoint Online** 및 비즈니스용 OneDrive 이 DEP는 SPO에 저장된 파일을 포함하여 SPO 및 비즈니스용 OneDrive 콘텐츠를 Microsoft Teams 데 사용됩니다. Multi-Geo 기능을 사용하는 경우 조직에 대해 지리적으로 DEP를 하나씩 만들 수 있습니다. Multi-Geo 기능을 사용하지 않는 경우 테넌트당 DEP를 하나만 만들 수 있습니다. 고객 키 설정 [의 세부 정보를 참조합니다.](customer-key-set-up.md)

### <a name="encryption-ciphers-used-by-customer-key"></a>고객 키에서 사용하는 암호화 암호화

고객 키는 다음 그림과 같이 다양한 암호화 암호화를 사용하여 키를 암호화합니다.

여러 Microsoft 365 작업의 데이터를 암호화하는 DEP에 사용되는 주요 계층 구조는 개별 사서함의 DEP에 사용되는 Exchange Online 비슷합니다. 유일한 차이점은 사서함 키가 해당 작업 키로 Microsoft 365 것입니다.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Exchange Online 암호화하는 데 사용되는 암호화 비즈니스용 Skype

![고객 키에 대한 Exchange Online 암호화입니다.](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online, 비즈니스용 OneDrive 및 Teams 암호화

![온라인 고객 SharePoint 암호화.](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>관련 문서

- [고객 키 설정](customer-key-set-up.md)

- [고객 키 관리](customer-key-manage.md)

- [고객 키 또는 가용성 키 롤 또는 회전](customer-key-availability-key-roll.md)

- [가용성 키에 대해 자세히 알아보기](customer-key-availability-key-understand.md)

- [고객 Lockbox](customer-lockbox-requests.md)

- [서비스 암호화](office-365-service-encryption.md)