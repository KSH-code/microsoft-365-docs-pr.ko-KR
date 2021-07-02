---
title: 도구 OneDrive Learning 사용
ms.author: v-cichur
author: cichur
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
description: 과제를 만들고 등급을 지정하고, 과정 콘텐츠를 작성 및 구성하고, 새로운 OneDrive Learning 도구 상호 관리 앱을 사용하여 실시간으로 파일을 공동으로 작업합니다.
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256987"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a>Canvas에서 Microsoft OneDrive LTI 사용

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

## <a name="integrate-with-canvas"></a>Canvas와 통합

이 통합을 수행하는 사용자는 Canvas의 관리자이자 테넌트의 Microsoft 365 합니다.

1. 테넌트 관리자 계정으로 Microsoft Azure 포털에 로그인합니다. Azure 테넌트 관리자에게도 그룹 관리자 역할이 있습니다.

    ![그룹 관리자가 강조 표시](../media/lti-media/lti-group-admin.png)

2. Microsoft OneDrive [LTI 포털에 로그인합니다.](https://odltiappnl.azurewebsites.net/admin)

3. 로그인을 완료하려면 사용 권한을 수락합니다.

    ![사용 권한 수락](../media/lti-media/lti-permissions.png)

4. LTI **테넌트 추가를 선택합니다.**

     ![LTI 테넌트 추가](../media/lti-media/lti-add-tenant.png)

5. **드롭다운에서 LTI 소비자** 플랫폼을 **캔버스로** 선택합니다.

6. 캔버스 **기본 URL을 선택하고** 다음 을 **선택합니다.**

    ![캔버스를 선택하고 기본 URL 추가](../media/lti-media/lti-canvas-base-url.png)

   다음 화면에는 기밀 필드가 표시됩니다.

7. **?에서 다음을** 선택합니다. 페이지. 검토자는 여기에서 공백을 채울 수 있나요?

8. **화면에서** 기밀 정보를 표시하는 다음을 선택합니다.

   Azure Portal의 마지막 화면에는 Canvas 인스턴스를 추가하기 위한 다음 단계가 표시됩니다.

9. 이 화면에서 개발자 키를 복사합니다. Canvas 인스턴스를 만들 때 사용할 수 있습니다.

## <a name="add-the-canvas-instance"></a>Canvas 인스턴스 추가

1. Canvas 인스턴스에서 관리자 개발자 **키의**  >  **선택을 선택합니다.**

2. 개발자 **키의** 드롭다운에서 LTI **키를 선택하세요.**

   ![LTI 개발자 키 얻기](../media/lti-media/lti-developer-keys.png)

3. 여기에 개발자 키를 붙여 넣습니다.

     ![개발자 키 붙여넣기](../media/lti-media/lti-developer-keys.png)

   키가 **꺼진** 모드에서 생성됩니다.

   ![오프 모드에서 생성된 개발자 키](../media/lti-media/lti-copy-developer-keys.png)

4. 강조 표시된 텍스트를 복사합니다.
    이 ID는 LTI 포털에서 Microsoft OneDrive 역할을 합니다.

5. LTI 포털의 클라이언트 **ID** 필드에 텍스트를 Microsoft OneDrive 다음 을 **선택합니다.**

6. **저장** 을 선택합니다.

7. LTI 테넌트 보기 를 선택하여 **설정을 확인합니다.**
