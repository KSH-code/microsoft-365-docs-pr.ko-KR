---
title: Teams 관리 센터에서 Microsoft Viva Learning(미리 보기) 설정
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/24/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Teams 관리 센터에서 Microsoft Viva Learning(미리 보기)을 구성하는 방법을 자세히 알아보습니다.
ms.openlocfilehash: a96a2f3ecf7d4e1ee0c136ae155868218f08aaf4
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636137"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>Teams 관리 센터에서 Microsoft Viva Learning(미리 보기) 설정

> [!NOTE]
> 이 문서의 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 보기 제품과 관련이 있습니다. 

Teams 관리자는 Viva Learning(미리 보기)을 설치하고 Teams 관리 센터를 통해 권한 정책을 적용합니다.

1. Viva Learning(미리 보기)의 경우 먼저 업데이트 정책에서 Teams. 자세한 내용은 공개 미리 [Microsoft Teams 참조하세요.](/MicrosoftTeams/public-preview-doc-updates)

    1. Teams 센터에 로그인합니다.

    2. 업데이트 **Teams**  >  **선택합니다.**

    3. **추가** 를 선택합니다. 

    4. 업데이트 정책의 이름을 지정하고 정책을 추가한 다음 미리 보기 기능 **표시를 켜야 합니다.**

2. 관리자는 사용자에게 정책 업데이트를 알려 해당 빌드를 공용 미리 보기로 이동해야 Teams. 

    1. 사용자는 공개 미리 보기 정보에서 > **이미지를**  >  **선택해야 합니다.**
   
        ![사용자 프로필을 Teams 응용 프로그램의 위쪽 탐색](../media/learning/learning-app-select-profile-teams.png)
    
    2. 사용자는 공개 미리 보기 **사용 약관에** 동의해야 합니다.

        ![공개 미리 보기 빌드로 전환](../media/learning/learning-app-switch-to-public-preview.png)
 
3. 제한적인 정책이 적용되어 있으며 Viva Learning(미리 보기)을 사용하도록 설정해야 하는 조직의 경우 다음 섹션의 프로세스를 따르십시오.

## <a name="manage-settings-for-viva-learning-preview"></a>Viva Learning 설정 관리(미리 보기)

이러한 작업을 수행하려면 Teams 관리 센터의 관리자 되어야 합니다.

조직의 사용자가 Viva Learning(미리 보기)을 사용할 수 있도록 설정하기 위해 다음 단계를 수행합니다.

1. Teams 센터의 왼쪽 탐색 창에서 앱 관리 **Teams 로**  >  **이동하세요.**

   ![앱 및 앱 Teams 섹션을 Teams 관리 센터의 왼쪽 탐색입니다.](../media/learning/learning-app-teams-manage-apps-nav.png)

2. 앱 **관리 페이지의** 검색 상자에 *Viva learning* 을 입력하고 **Viva Learning(미리 보기)을 선택합니다.**

   ![검색 상자를 표시하는 Teams 관리 센터의 앱 페이지 관리](../media/learning/learning-app-teams-manage-apps-page.png)

3. **Viva Learning(미리 보기) 페이지에서 다음을** 클릭합니다.

   1. 상태 **아래에서** Viva Learning 켜기 허용(미리 보기)을 선택합니다. 

   2. 설정 **탭의** 앱 설정에서 Microsoft 365 관리 센터로 이동하여 학습 콘텐츠 원본을 [구성합니다.](content-sources-365-admin-center.md)

   ![상태 및 앱 설정 Teams 관리 센터의 학습 페이지입니다.](../media/learning/learning-app-teams-learning-page.png)

4. 앱 **설정 관리** 후  사용  권한 정책 및 설정 정책으로 이동하여 조직의 미리 보기 참여의 일부로 Viva Learning(미리 보기)에 액세스할 수 있는 권한을 직원에게 부여합니다.

> [!NOTE]
>  조직이 TAP100 프로그램의 일부로 Teams 링 4.0에 있는 경우 링 3.0에서 승인된 사용자가 Viva Learning(미리 보기)에 액세스하도록 설정해야 할 수 있습니다. <br><br>미리 보기의 일부로 Viva Learning(미리 보기)은 링 3.0에서 릴리스됩니다. 조직이 링 4.0에 있는 경우 앱 관리 페이지에 Viva Learning(미리 보기)이 **표시되지** 않습니다. 앱을 테스트하려면 사용자 지정 앱 사용 권한 정책을 만들고, 모든 앱 허용으로 설정하고, 링 3.0 승인된 사용자에게 할당해야 합니다.  <br><br>   ![TAP-AppsPermission-Plcy 페이지에는 모든 앱 허용이 선택되어 있습니다.](../media/learning/learning-app-tap-appspermission-plcy.png)

## <a name="next-step"></a>다음 단계

[Microsoft 365 관리 센터에서 Viva Learning(미리 보기)에 대한 학습 콘텐츠 원본 구성](content-sources-365-admin-center.md)
