---
title: Microsoft가 아닌 클라우드 앱에 데이터 손실 방지 정책 사용(미리 보기)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft가 아닌 클라우드 앱에 대해 dlp 정책을 사용하는 방법을 배워야 합니다.
ms.openlocfilehash: 6787add3ef8b2d6ded22bd05c0ff9658c4b7fbfc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922084"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>Microsoft가 아닌 클라우드 앱에 데이터 손실 방지 정책 사용(미리 보기)

Microsoft가 아닌 클라우드 앱에 대한 DLP(데이터 손실 방지) 정책은 Microsoft 365 DLP 기능 제품군의 일부입니다. 이러한 기능을 사용하여 Microsoft 365 서비스에서 중요한 항목을 검색하고 보호할 수 있습니다. 모든 Microsoft DLP 제공에 대한 자세한 내용은 데이터 손실 방지 [개요를 참조하세요.](./data-loss-prevention-policies.md?view=o365-worldwide)

DLP 정책을 사용하여 Microsoft가 아닌 클라우드 앱에 중요한 항목이 사용되는 경우를 모니터링하고 Microsoft가 아닌 클라우드 앱을 통해 공유할 수 있습니다. 이러한 정책을 사용하면 정책이 올바르게 사용 및 보호되도록 하는 데 필요한 가시성과 제어가 제공될 수 있으며, 이를 통해 손상될 수 있는 위험한 동작을 방지할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

### <a name="skusubscriptions-licensing"></a>SKU/구독 라이선싱

Microsoft가 아닌 클라우드 앱에 DLP 정책을 사용하려면 [먼저 Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) 구독 및 추가 기능을 확인하세요. 이 기능에 액세스하고 사용하려면 다음 구독 또는 추가 기능 중 하나만 있어야 합니다.

- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft 365 E5 Security

### <a name="prepare-your-cloud-app-security-environment"></a>Cloud App Security 환경 준비

Microsoft가 아닌 클라우드 앱에 대한 DLP 정책은 Cloud App Security DLP 기능을 사용 합니다. 클라우드 앱 보안 환경을 준비해야 합니다. 지침은 앱에 대한 즉각적인 가시성, 보호 [및 거버넌스 작업 설정 을 참조하세요.](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)

### <a name="connect-a-non-microsoft-cloud-app"></a>Microsoft가 아닌 클라우드 앱 연결

DLP 정책을 사용하여 Microsoft가 아닌 특정 클라우드 앱에 사용하려면 앱을 Cloud App Security에 연결해야 합니다. 자세한 내용은 다음을 참조하세요.

- [Connect Box](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Connect Dropbox](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [G-Suite 연결](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Connect Salesforce](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Cisco Webex 연결](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

클라우드 앱을 Cloud App Security에 연결한 후 클라우드 앱을 위한 Microsoft 365 DLP 정책을 만들 수 있습니다.

>[!NOTE]
>Microsoft Cloud App Security를 사용하여 Microsoft 클라우드 앱에 대한 DLP 정책을 만들 수 있습니다. 그러나 Microsoft 365를 사용하여 Microsoft 클라우드 앱에 대한 DLP 정책을 만들고 관리하는 것이 좋습니다.

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Microsoft가 아닌 클라우드 앱에 대한 DLP 정책 만들기

DLP 정책의 위치를 선택하면 Microsoft Cloud **App Security 위치를 켜야** 합니다.

- 특정 앱 또는 인스턴스를 선택하려면 인스턴스 **선택 을 선택합니다.**
- 인스턴스를 선택하지 않은 경우 정책은 Microsoft Cloud App Security 테넌트의 연결된 모든 앱을 사용 합니다.

   ![정책을 적용할 위치](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US 및 Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

지원되는 모든 비 Microsoft 클라우드 앱에 대해 다양한 작업을 선택할 수 있습니다. 모든 앱에 대해 가능한 작업이 다릅니다(클라우드 앱 API에 따라 다름).

![규칙 만들기](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

DLP 정책에서 규칙을 만들 때 Microsoft가 아닌 클라우드 앱에 대한 작업을 선택할 수 있습니다. 타사 앱을 제한하려면 타사 앱 **제한을 선택합니다.**

![타사 앱 제한](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

DLP 정책을 만들고 구성하는 데 대한 자세한 내용은 [Create test and tune a DLP policy 를 참조하십시오.](./create-test-tune-dlp-policy.md?view=o365-worldwide)

## <a name="see-also"></a>참고 항목

- [테스트 만들기 및 DLP 정책 조정](./create-test-tune-dlp-policy.md?view=o365-worldwide)
- [기본 DLP 정책을 사용하여 시작](./get-started-with-the-default-dlp-policy.md?view=o365-worldwide)
- [서식 파일에서 DLP 정책 만들기](./create-a-dlp-policy-from-a-template.md?view=o365-worldwide)