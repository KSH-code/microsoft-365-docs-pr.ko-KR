---
title: Go1을 콘텐츠 원본으로 Microsoft Viva Learning
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/07/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: Go1을 사용자용 학습 콘텐츠 원본으로 구성하는 Microsoft Viva Learning.
ROBOTS: NOINDEX
ms.openlocfilehash: ade44c0cc7607ab1b7a247ee60bdd2ca3505e6e9
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60586164"
---
# <a name="configure-go1-as-a-content-source-for-microsoft-viva-learning"></a>Go1을 콘텐츠 원본으로 Microsoft Viva Learning

>[!NOTE]
>이 기능은 미리 보기에서 지원되지 않습니다.

이 문서에서는 Viva 2013에서 Go1을 타사 학습 콘텐츠 원본으로 구성하는 Learning.

>[!NOTE]
>Viva Learning 액세스할 수 있는 콘텐츠에는 Microsoft 제품 약관이 없는 약관이 적용될 수 있습니다. Go1 콘텐츠 및 관련 서비스는 Go1의 개인 정보 및 서비스 약관을 준수합니다.

Go1에서는 상위 콘텐츠 공급자로부터 수천 개의 과정에 액세스할 수 있습니다. [자세한 내용은 Go1 을(를) 자세히 알아보아야 할 수 있습니다.](https://www.go1.com/go1-microsoft-viva) 다음 단계에 따라 Viva 2013에서 Go1을 학습 원본으로 Learning.

## <a name="create-a-developers-app-in-go1"></a>Go1에서 개발자 앱 만들기

먼저 다음 단계에 따라 Go1 포털에서 앱을 만들어야 합니다. 이 앱은 GO1을 인증하고 API에 대한 요청을 하는 데 사용할 수 있는 API 키를 생성합니다.

1. Go1 포털에 관리자로 로그인합니다.

2. 메뉴 **옵션에서** 통합을 선택합니다.

3. 개발자를 **선택합니다.**

    <!--![Image of the Developers option in the Integrations menu.](../media/learning/go1-1.png)-->

4. 앱 **만들기 단추를** 선택합니다.

    <!--![Image of the Create App button.](../media/learning/go1-2.png)-->

5. 앱의 이름(예: "My-go1-viva-integration")을 입력합니다.

6. 전화 걸기 URL(예: "Mycompany.mygo1.com")을 입력합니다.

    <!--![Image of the field where you enter the name and callback URL.](../media/learning/go1-3.png)-->

7. 입력한 정보를 저장합니다.

8. 비밀이 숨겨져 있는 정보로 표시됩니다. 타원(**...**)을 선택한 다음 **비밀** 보기를 선택하여 비밀을 표시합니다.

9. 다음 값을 복사합니다.

    - **클라이언트의 호스트 URL:** Go1 포털 URL입니다. " https://mycompany.mygo1.com "처럼 보입니다.
    - **클라이언트 ID:** 통합/개발자 메뉴 옵션의 Go1 **포털에서 ID를 찾을** 수 있습니다.
    - **비밀:** Go1 포털의 **통합/개발자** 메뉴 옵션에서 비밀을 찾을 수 있습니다.

## <a name="complete-configuration-in-the-microsoft-365-admin-center"></a>전체 구성은 Microsoft 365 관리 센터

Go1 Portal에서 검색한 값을 복사하여 검색한 값을 이동 화면의 Go1 설정 화면에 Microsoft 365 관리 센터.

Go1용 개인 개발자 앱을 만드는 [방법에 대해 자세히 알아보하세요.](https://help.go1.com/en/articles/4642648-integrate-with-the-go1-api)
