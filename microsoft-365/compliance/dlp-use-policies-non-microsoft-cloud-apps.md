---
title: Microsoft 제품이 아닌 클라우드 앱에 대해 데이터 손실 방지 정책 사용 (미리 보기)
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
description: 타사 클라우드 앱에 대해 dlp 정책을 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: dd5a7a4bc0725d0785daec6b7635047cd91f20a2
ms.sourcegitcommit: 39af527404cb06e05c5aa4550dbec39aec133016
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48422760"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>Microsoft 제품이 아닌 클라우드 앱에 대해 데이터 손실 방지 정책 사용 (미리 보기)

Microsoft 제품이 아닌 클라우드 앱에 대 한 DLP (데이터 손실 방지) 정책은 Microsoft 365 DLP 기능 집합의 일부입니다. 이러한 기능을 사용 하면 Microsoft 365 서비스에서 중요 한 항목을 검색 및 보호할 수 있습니다. 모든 Microsoft DLP 제공에 대 한 자세한 내용은 [Overview For data 손실 방지](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)를 참조 하십시오.

Microsoft 제품이 아닌 클라우드 앱에 대해 DLP 정책을 사용 하 여 중요 한 항목을 사용 하 고 공유 하는 시간을 모니터링 하 고 검색할 수 있습니다. 이러한 정책을 사용 하면 올바르게 사용 및 보호 되는지 확인 하는 데 필요한 가시성 및 제어를 얻을 수 있으며,이를 통해 손상 될 수 있는 위험한 동작이 방지 됩니다.

## <a name="before-you-begin"></a>시작하기 전에

### <a name="skusubscriptions-licensing"></a>SKU/구독 라이선싱

Microsoft 이외의 클라우드 앱에 DLP 정책을 사용 하기 전에 [microsoft 365 구독](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) 및 모든 추가 기능을 확인 합니다. 이 기능에 액세스 하 고 사용 하려면 다음 구독 또는 추가 기능 중 하나가 있어야 합니다.

- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft 365 E5 Security

### <a name="prepare-your-cloud-app-security-environment"></a>Cloud App Security 환경 준비

비 Microsoft 클라우드 앱에 대 한 DLP 정책은 Cloud App Security DLP 기능을 사용 합니다. 이 도구를 사용 하려면 Cloud App Security environment를 준비 해야 합니다. 자세한 내용은 [앱에 대 한 isntant visibility, protection 및 관리 작업 설정](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)를 참조 하세요.

### <a name="connect-a-non-microsoft-cloud-app"></a>타사 클라우드 앱 연결

Microsoft 제품이 아닌 특정 클라우드 앱에 DLP 정책을 사용 하려면 앱이 Cloud App Security에 연결 되어 있어야 합니다. 자세한 내용은 다음 항목을 참조 하십시오.

- [연결 상자](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Dropbox 연결](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [G-제품군 연결](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Salesforce 연결](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Cisco Webex 연결](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

클라우드 앱을 Cloud App Security에 연결한 후에는 Microsoft 365 DLP 정책을 만들 수 있습니다.

>[!NOTE]
>Microsoft Cloud App Security를 사용 하 여 Microsoft 클라우드 앱에 DLP 정책을 만들 수도 있습니다. 그러나 microsoft 클라우드 앱에 DLP 정책을 만들고 관리 하는 데에는 마이크로소프트 365를 사용 하는 것이 좋습니다.

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>비 Microsoft cloud app에 대 한 DLP 정책 만들기

DLP 정책에 대 한 위치를 선택 하는 경우 **Microsoft Cloud App Security** 위치를 설정 합니다.

- 특정 앱 또는 인스턴스를 선택 하려면 **인스턴스 선택을**선택 합니다.
- 인스턴스를 선택 하지 않으면 정책에서 Microsoft Cloud App Security 테 넌 트에 연결 된 모든 앱을 사용 합니다.

   ![정책을 적용할 위치](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![박스 및 Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

지원 되는 Microsoft cloud가 아닌 모든 클라우드 앱에 대해 다양 한 작업을 선택할 수 있습니다. 모든 앱에 대해 다양 한 작업을 수행할 수 있습니다 (cloud app API에 따라 다름).

![규칙 만들기](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

DLP 정책에서 규칙을 만들 때 비 Microsoft 클라우드 앱에 대 한 작업을 선택할 수 있습니다. 타사 앱을 제한 하려면 타사 **앱 제한을**선택 합니다.

![타사 앱 제한](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

DLP 정책을 만들고 구성 하는 방법에 대 한 자세한 내용은 [Create test and expressiona dlp policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)을 참조 하십시오.

## <a name="see-also"></a>참고 항목

- [테스트 만들기 및 DLP 정책 튜닝](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [기본 DLP 정책을 사용하여 시작](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [서식 파일에서 DLP 정책 만들기](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
