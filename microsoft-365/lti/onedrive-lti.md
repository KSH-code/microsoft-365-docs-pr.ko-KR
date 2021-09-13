---
title: 도구 Microsoft OneDrive Learning 사용
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 과제를 만들고 등급을 지정하고, 과정 콘텐츠를 작성 및 구성하고, 새로운 Microsoft OneDrive Learning 도구 상호 관리 앱을 사용하여 실시간으로 파일을 공동 작업합니다.
ms.openlocfilehash: e67e772ce8ef460075729b34bc7da86d486c51e9
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189559"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a>Canvas Microsoft OneDrive LTI 통합

> [!IMPORTANT]
> 일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 사전 출시 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

LTI를 Microsoft OneDrive 통합하는 과정은 두 단계로 진행됩니다. 첫 번째 단계에서는 Canvas에서 Microsoft OneDrive 사용할 수 있으며, 두 번째 단계에서는 Canvas Microsoft OneDrive LTI를 사용할 수 있도록 합니다.

## <a name="recommended-browser-settings"></a>권장 브라우저 설정

- 쿠키를 사용할 수 Microsoft OneDrive.
- 팝업은 차단하지 말아야 Microsoft OneDrive.

> [!NOTE]
> - 쿠키는 Chrome 브라우저의 시그니치 모드에서 기본적으로 사용하도록 설정되지 않습니다. 이 경우 쿠키를 사용하도록 설정해야 합니다.
> - Microsoft OneDrive LTI는 브라우저의 개인 모드에서 Microsoft Edge 작동합니다. 기본적으로 사용하도록 설정된 쿠키를 차단하지 않은지 확인합니다.

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a>Canvas에서 Microsoft OneDrive LTI 사용

> [!IMPORTANT]
> 이 통합을 수행하는 사람은 Canvas의 관리자이자 테넌트의 Microsoft 365 합니다.

1. LTI Microsoft OneDrive <a href="https://onedrivelti.microsoft.com/admin" target="_blank">포털에 로그인합니다.</a>
1. 관리자 **동의 단추를** 선택하고 사용 권한을 수락합니다.

> [!CAUTION]
> 이 단계를 수행하지 않은 경우 다음 단계를 수행하면 오류가 발생하고 한 시간 동안 이 단계를 수행할 수 없습니다.

3. 새 **LTI 테넌트 만들기 단추를** 선택합니다. LTI 등록 페이지에서 드롭다운에서 **캔버스를** 선택하고 Canvas 인스턴스의 기본 URL을 입력합니다.

> [!NOTE]
> Canvas 인스턴스가 ]()인 경우 https://contoso.test.instructure.com https://contoso.test.instructure.com) 전체 URL을 입력해야 합니다.

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="LTI 소비자 플랫폼 및 URL 텍스트 필드를 선택하기 위한 드롭다운 필드가 있는 LTI 테넌트 관리 페이지":::

4. 복사 단추(오른쪽에 두  페이지를 표시하는 아이콘)를 선택하여 JSON을 복사합니다. 이 키는 Canvas에서 키를 생성하는 데 사용됩니다.

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="표시된 JSON 텍스트를 복사하고 Canvas에서 키 생성에 사용할 수 있도록 하는 복사 단추를 보여 주는 이미지입니다.":::

5. 관리자 권한으로 Canvas 인스턴스에  로그인하고 페이지 왼쪽 메뉴에서 개발자 키를 선택합니다. 드롭다운에서 페이지 오른쪽 위에 있는 드롭다운에서 **LTI** 키를 선택하여 개발자 키를 만드십시오.

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="개발자 키가 선택된 왼쪽 탐색 모음과 페이지 오른쪽의 드롭다운에서 LTI 키 항목을 선택한 스크린샷":::

6. 구성 페이지의 메서드 드롭다운에서 **메서드로 JSON** 붙여넣기 를 선택하고 5단계에서 복사한 JSON 텍스트를 나타나는 텍스트 필드에 붙여 넣습니다. 
7. 키를 저장하면 Canvas에서 Off 상태로 사용할 **수** 있습니다. 키를 **켜고** 다음 단계에서 사용할  세부 정보 열에 제공된 키를 복사합니다.

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="키가 꺼진 상태로 설정된 Canvas 페이지입니다. 이 키를 켜야 합니다. 이 페이지의 세부 정보 열에서 키를 복사해야 합니다.":::

8. LTI Microsoft OneDrive 포털로 돌아가 캔버스 클라이언트 ID 필드에 키를 **붙여 넣습니다.** 준비가 **되면** 다음을 선택합니다.

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="키를 복사해야 하는 JSON 텍스트와 텍스트 상자를 보여 주며 LTI 테넌트 등록 페이지입니다.":::

9. 변경 내용을 검토하고 저장합니다. 성공적인 등록 시 메시지가 표시됩니다.
10. 홈 페이지에서 **LTI** 테넌트 보기 단추를 선택하여 등록 세부 정보를 검토할 수도 있습니다.

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a>Canvas Microsoft OneDrive LTI 사용

Canvas 관리자는 모든 Microsoft OneDrive LTI를 사용하도록 설정할 수 있습니다. 특정 Microsoft OneDrive LTI가 필요한 경우(모든 과정이 아닌) 강사는 과정 설정 내에서 동일한 단계를 따라야 합니다.

1. 관리자로 로그인하고 설정 **섹션으로** 이동하세요.
2. 앱 **섹션으로 이동하여** 앱 구성 보기 **단추를** 선택합니다.
3. 앱 **추가 단추를** 선택합니다.
4. 구성 **유형 드롭다운에서** 클라이언트 **ID 옵션을** 선택합니다.
5. 이전에 클라이언트 ID 필드에 생성된 개발자 키 값을 **붙여넣고** 제출 **단추를** 선택합니다.

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="구성 유형 드롭다운 메뉴 아래에 클라이언트 ID 옵션을 표시하는 앱 추가 페이지입니다.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a>Canvas 설정 LTI에 Microsoft OneDrive 대한 공동 작업 작업

> [!NOTE]
> 교육자 및 학생을 위해 공동 작업을 진행하려면 공동 작업 설정을 사용하도록 설정하면 안 됩니다. 설정이 사용하도록 설정되어 있지 않은지 확인을 위해 아래 단계를 따르세요.

1. 관리자로 로그인하고 설정 **섹션으로** 이동하세요.
1. 기능 옵션 **섹션으로** 이동한 다음 과정 **섹션으로** 이동하십시오.
1. 외부 공동 **작업 도구** 기능을 사용하도록 설정합니다.

> [!NOTE]
> 개별 학생 및 학생 그룹에 공동 작업을 할당할 수 있습니다. 개별 학생에게 할당은 기본적으로 작동합니다. 학생 그룹에 공동 작업을 할당할 수 있는 경우 다음 단계를 수행합니다.

1. 관리자로 로그인하고 개발자 키 **섹션으로** 이동하세요.
1. 값이 있는 키를 170000000000710 으로 **설정하면 됩니다.**
