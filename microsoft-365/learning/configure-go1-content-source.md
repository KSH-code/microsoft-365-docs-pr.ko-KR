---
title: Go1을 콘텐츠 원본으로 Microsoft Viva Learning
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
description: Go1을 사용자용 학습 콘텐츠 원본으로 구성하는 Microsoft Viva Learning.
ms.openlocfilehash: 1adef6275be2a8656eaad9a7f47805d13299e3c7
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950536"
---
# <a name="configure-go1-as-a-content-source-for-microsoft-viva-learning"></a>Go1을 콘텐츠 원본으로 Microsoft Viva Learning

이 문서에서는 Viva 2013에서 Go1을 타사 학습 콘텐츠 원본으로 구성하는 Learning.

>[!NOTE]
>Viva Learning 액세스할 수 있는 콘텐츠에는 Microsoft 제품 약관이 없는 약관이 적용될 수 있습니다. Go1 콘텐츠 및 관련 서비스는 Go1의 개인 정보 및 서비스 약관을 준수합니다.

Go1에서는 상위 콘텐츠 공급자로부터 수천 개의 과정에 액세스할 수 있습니다. [자세한 내용은 Go1 을(를) 자세히 알아보아야 할 수 있습니다.](https://www.go1.com/go1-microsoft-viva) 다음 단계에 따라 Viva 2013에서 Go1을 학습 원본으로 Learning.

## <a name="configure-in-your-go1-portal"></a>Go1 포털에서 구성

>[!NOTE]
>이 단계를 완료하려면 Go1에서 관리자 권한이 필요합니다.

먼저 다음 단계에 따라 Go1 포털에서 앱을 만들어야 합니다. 이 앱은 GO1을 인증하고 API에 대한 요청을 하는 데 사용할 수 있는 API 키를 생성합니다.

1. Go1 포털에 관리자로 로그인합니다.

2. 메뉴 **옵션에서** 통합을 선택합니다.

3. 개발자를 **선택합니다.**
4. 앱 **만들기 단추를** 선택합니다.
5. 앱의 이름(예: "My-go1-viva-integration")을 입력합니다.
6. 전화 걸기 URL(예: "Mycompany.mygo1.com")을 입력합니다.
7. 입력한 정보를 저장합니다.
8. 비밀이 숨겨져 있는 정보로 표시됩니다. 타원(**...**)을 선택한 다음 **비밀** 보기를 선택하여 비밀을 표시합니다.
9. 다음 값을 복사합니다.

    - **클라이언트의 호스트 URL:** Go1 포털 URL입니다. " https://mycompany.mygo1.com "처럼 보입니다.
    - **클라이언트 ID:** 통합/개발자 메뉴 옵션의 Go1 **포털에서 ID를 찾을** 수 있습니다.
    - **비밀:** Go1 포털의 **통합/개발자** 메뉴 옵션에서 비밀을 찾을 수 있습니다.

Go1용 개인 개발자 앱을 만드는 [방법에 대해 자세히 알아보하세요.](https://help.go1.com/en/articles/4642648-integrate-with-the-go1-api)

## <a name="configure-in-your-microsoft-365-admin-center"></a>사용자 설정에서 Microsoft 365 관리 센터

>[!NOTE]
>이러한 단계를 완료하려면 관리자 권한이 Microsoft 365 합니다.

1. 에 [로그인합니다Microsoft 365 관리 센터.](https://admin.microsoft.com)
2. 다음 **설정** **로 이동합니다.** Viva Learning 선택하고 패널에서 Go1을 사용하도록 설정합니다.
3. Go1 포털에서 검색한 구성 세부 정보를 입력합니다.
4. **저장을** 선택하여 Viva 2013에서 Go1 콘텐츠를 Learning. Viva 앱에 콘텐츠가 표시될 때 최대 24시간이 Learning 있습니다.
