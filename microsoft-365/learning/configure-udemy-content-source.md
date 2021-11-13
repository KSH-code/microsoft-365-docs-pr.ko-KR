---
title: Udemy를 콘텐츠 원본으로 Microsoft Viva Learning
ms.author: daisyfeller
author: daisyfell
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
description: Udemy를 사용자용 학습 콘텐츠 원본으로 구성하는 Microsoft Viva Learning.
ms.openlocfilehash: ea015d6ee0ec1890d56b6f40f928fe96ea44ccbc
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950584"
---
# <a name="configure-udemy-as-a-content-source-for-microsoft-viva-learning"></a>Udemy를 콘텐츠 원본으로 Microsoft Viva Learning

이 문서에서는 Udemy를 사용자용 타사 학습 콘텐츠 원본으로 구성하는 Microsoft Viva Learning.

>[!NOTE]
>Viva Learning 액세스할 수 있는 콘텐츠에는 Microsoft 제품 약관이 없는 약관이 적용될 수 있습니다. Udemy 콘텐츠 및 모든 관련 서비스는 Udemy의 개인 정보 및 서비스 약관을 준수합니다.

## <a name="configure-in-your-udemy-portal"></a>Udemy 포털에서 구성

>[!NOTE]
>이 단계를 완료하려면 Udemy에서 관리자 권한이 필요합니다.

다음 단계에 따라 Udemy Business 환경에서 API를 사용하도록 설정하고 LMS/LXP 응용 프로그램에 대한 클라이언트 자격 증명을 생성하여 API에 액세스합니다.

1. 관리로 **이동한** **설정** API **를 검색합니다.** API의 상태를 검사합니다. 사용하지 않도록 설정된 경우 지원 팀에 문의하여 사용하도록 설정하거나 아래 단계에 따라 사용하도록 설정할 수 있습니다.

    ![API 설정 페이지의 이미지입니다.](../media/learning/udemy-1.png)

2. API를 사용하지 않도록 설정한 경우 **LMS/LXP** 통합으로 이동한 다음 **설정** 시작, 기타 로 **이동합니다.**

    [![LMS/LXP 통합 설정 페이지의 이미지입니다.](../media/learning/udemy-2small.png)](../media/learning/udemy-2.png#lightbox)

3. 다음 화면에서 사용자 지정 LMS/LXP 또는 타사 응용 프로그램의 이름을 입력합니다. 그런 다음 자동 등록 옵션을 켜거나 끄고 저장을 **선택합니다.** 자동 등록 옵션을 사용하면 LMS/LXP를 통해 과정을 시작한 사용자가 자동으로 Udemy에 등록할 수 있습니다.

    ![자동 등록에 대한 on/off 토글의 이미지입니다.](../media/learning/udemy-3.png)

4. 저장한 후 클라이언트 ID 및 클라이언트 비밀이 생성되고 화면에서 복사할 수 있습니다. 이제 제공된 클라이언트 자격 증명을 사용하여 API에 액세스할 수 있습니다.

    ![생성된 클라이언트 ID 및 클라이언트 비밀의 이미지입니다.](../media/learning/udemy-4.png)

5. API 끝점에 액세스하려면 API 끝점 및 ACCOUNT_ID URL이 필요합니다. 이 정보에 액세스한 다음 관리 , 다음 API로 설정 API를 사용해 볼 수 **있습니다.**  API를 사용하도록 설정하면 API의 상태가 "사용"으로 표시됩니다. API 설명서 링크를 선택합니다.

    ![API가 활성화된 것으로 표시되어 있는 API 설정의 이미지입니다.](../media/learning/udemy-5.png)

6. 개요 페이지에서 API 끝점 URL을 ACCOUNT_ID URL을 확인합니다. 지원되는 메서드로 이동하여 API 호출을 시도합니다. 이제 모두 Udemy Business API를 호출할 수 있습니다.

    ![끝점 URL 및 클라이언트 ID를 표시하는 개요 페이지의 이미지입니다.](../media/learning/udemy-6.png)
    ![URL 및 클라이언트 ID를 입력할 수 있는 직접 시도 페이지의 이미지입니다.](../media/learning/udemy-7.png)

## <a name="configure-in-your-microsoft-365-admin-center"></a>사용자 설정에서 Microsoft 365 관리 센터

>[!NOTE]
>이러한 단계를 완료하려면 관리자 권한이 Microsoft 365 합니다.

이전 단계를 사용하여 Udemy 포털에서 필요한 구성 세부 정보를 받은 후 테넌트 관리자는 다음 단계를 사용하여 Udemy를 Microsoft 365 관리 센터 구성해야 합니다.

1. 에서 [로 Microsoft 365 관리 센터.](https://admin.microsoft.com)

2. 다음 **설정** **로 이동합니다.** Viva Learning 검색하고 옵션에서 Udemy를 사용하도록 설정할 수 있습니다.

3. 다음과 같은 필수 구성 세부 정보를 입력합니다.

    - **클라이언트의 호스트 URL**: 6단계에서 Udemy 포털에서 수집한 API 끝점 URL입니다.
    - **조직 ID:** 6단계에서 ACCOUNT_ID Udemy 포털에서 수집한 정보입니다.
    - **클라이언트 ID:** 4단계에서 Udemy 포털에서 수집한 클라이언트 ID입니다.
    - **클라이언트 비밀:** 4단계에서 Udemy 포털에서 수집한 클라이언트 비밀입니다.

4. **저장을** 선택하여 Udemy 콘텐츠의 활성화를 Microsoft Viva Learning. Viva 2013에서 콘텐츠를 사용할 수 있는 데 최대 24시간이 Learning.
