---
title: 사용자용 다른 콘텐츠 공급자 Microsoft Viva Learning
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/27/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: 다른 콘텐츠 공급자를 웹용 학습 콘텐츠 원본으로 구성하는 Microsoft Viva Learning.
ms.openlocfilehash: 4f1a8810f6b8615baa7e8b3fcd8d945ca08cf1d5
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60668267"
---
# <a name="add-other-content-providers-for-microsoft-viva-learning"></a>사용자용 다른 콘텐츠 공급자 Microsoft Viva Learning

Viva 및 Viva를 통해 점점 더 많은 학습 콘텐츠 공급자 집합을 Learning. 이 집합은 더 많은 공급자가 프로그램에 참여하거나 프로그램을 통해 상태를 변경하면 변경될 수 있습니다.

일부 학습 원본은 기본적으로 사용하도록 설정되어 있으며 프리미엄 Viva Learning 사용할 수 있습니다. 이러한 학습 원본은 다음과 같습니다.

- LinkedIn Learning 125개 과정 선택
- Microsoft Learn
- Microsoft 365 교육

타사 콘텐츠 원본은 기본적으로 사용하도록 설정되어 있지 않습니다. 이러한 원본을 사용하도록 설정하려면 [](content-sources-365-admin-center.md#configure-settings-for-the-learning-content-sources) 다음 표에 나와 있는 특정 Microsoft 365 관리 센터 추가해야 합니다.

>[!NOTE]
>LinkedIn Premium 무료 과정을 제외하고 외부 콘텐츠 원본을 연결하려면 Learning 라이선스가 필요합니다. [라이선스에 대해 자세히 알아보시다.](https://www.microsoft.com/microsoft-viva/learning)

>[!NOTE]
>Viva 사용자가 관리 포털에서 사용하도록 설정한 Learning 콘텐츠를 보는 데 24~48시간이 걸릴 수 있습니다. LinkedIn에서 콘텐츠를 숨기는 데 24~48시간이 걸릴 수도 Learning Microsoft Learn and Microsoft 365 trainings from Viva Learning after you have disabled them in the admin portal.

|콘텐츠 공급자  |구성 지침  |
|---------|---------|
|Go1     |[Go1을 콘텐츠 원본으로 구성](configure-go1-content-source.md)         |
|Skillsoft     |[Skillsoft를 콘텐츠 원본으로 구성](configure-skillsoft-content-source.md)         |
|Udemy   |[Udemy를 콘텐츠 원본으로 구성](configure-udemy-content-source.md)         |
|edX    |아래 단계에 따라 사용자 설정에 edX를 Microsoft 365 관리 센터.    |
|코스라    |아래 단계에 따라 사용자 설정에 과정 Microsoft 365 관리 센터.    |
|Pluralsight    |다음 단계에 따라 사용자 설정에 Pluralsight를 Microsoft 365 관리 센터.    |
|Infosec    |아래 단계에 따라 사용자 설정에 Infosec을 Microsoft 365 관리 센터.    |
|Josh Bersin Academy    |아래 단계에 따라 사용자 목록에 Josh Bersin Academy를 Microsoft 365 관리 센터.    |

1. 에 [로그인합니다Microsoft 365 관리 센터.](https://admin.microsoft.com)
2. 다음 **설정** **로 이동합니다.** Viva Learning 선택하고 패널에서 선택한 콘텐츠 공급자 또는 학습 관리 시스템을 사용하도록 설정할 수 있습니다.
3. 세부 정보를 입력합니다.
4. **저장** 을 선택합니다.

>[!NOTE]
>사용 가능한 콘텐츠 공급자는 변경될 수 있습니다. 조직에 따라 여기에 나열된 것보다 더 많은 콘텐츠 공급자에 액세스할 수 있습니다.

## <a name="content-ingestion-errors"></a>콘텐츠 검색 오류

콘텐츠가 검색되는 동안 Microsoft 365 관리 센터 발생하는 경우 다음 단계를 위해 아래 표를 참조하세요. 이 목록은 전체 목록으로, 향후 더 많은 오류 코드를 포함할 수 있습니다.

|콘텐츠 공급자 |오류 코드 |오류 코드 설명 |
|:----------------|:----------|:----------------------|
|모든 공급자 |USR_ERROR_INVALID_RESOURCE_CREDENTIALS |제공한 인증 자격 증명이 잘못되었습니다. 올바른 자격 증명을 입력해야 합니다. 자세한 내용은 Microsoft 고객 지원에 문의할 수 있습니다. |
|모든 공급자 |USR_ERROR_ACCESS_DENIED |파트너의 액세스가 거부됩니다. 입력한 자격 증명이 올바른지 확인하거나 콘텐츠 공급자의 지원 팀에 문의하세요. |

## <a name="content-consumption-for-end-users"></a>최종 사용자의 콘텐츠 소비

콘텐츠 공급자를 콘텐츠 원본으로 추가한 Microsoft 365 관리 센터 공급자의 콘텐츠는 Viva Learning 앱으로 흐르며 최종 사용자에게 표시됩니다.

사용자가 Viva Learning 강의를 재생하도록 선택하면 콘텐츠 공급자의 웹 페이지로 이동하고 공급자의 로그인 페이지에 로그인 자격 증명을 입력해야 합니다. [Viva 및 Viva를 통해](https://support.microsoft.com/office/01bfed12-c327-41e0-a68f-7fa527dcc98a)콘텐츠를 사용 하는 방법에 대해 Learning.
