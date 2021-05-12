---
title: OneDrive 학습 도구 상호 사용
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
description: 새 OneDrive 학습 도구 상호 관리 앱을 사용하여 과제를 만들고 등급을 지정하고, 과정 콘텐츠를 작성 및 구성하고, 실시간으로 파일을 공동 작업합니다.
ms.openlocfilehash: 97baf3e524e483e879d00f5e0c8495b450e13c92
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327742"
---
# <a name="use-microsoft-onedrive-with-your-learning-management-system"></a>학습 관리 시스템에 Microsoft OneDrive 사용

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

LMS(학습 관리 시스템)와 함께 Microsoft OneDrive를 사용할 때의 이점에 대해 자세히 알아보아야 합니다.

**워크플로에 Microsoft Office 365로 바로 연결**

Microsoft LTI(OneDrive Learning Tools Interoperability) 앱은 LMS와 통합되어 Microsoft OneDrive 및 Microsoft Office 365를 다음이 포함된 가장 중요한 워크플로로 바로 가져올 수 있습니다.

- 리소스 연결 및 콘텐츠 구성
- 공동 작업 문서 시작
- 배정 만들기 및 그라데이트

**최신 LTI 표준을 안전하고 완벽하게 준수**

Microsoft OneDrive LTI 앱은 LTI 1.3 및 LTI Advantage와 호환됩니다. 이러한 이점을 통해 보안이 강화되고 긴밀하게 통합된 사용자 환경을 사용할 수 있습니다.

**현대적이고 풍부한 사용자 환경**

Microsoft OneDrive LTI 앱은 Microsoft의 최고의 LMS 환경을 제공합니다. Microsoft는 새로운 확장된 Microsoft OneDrive 파일 선택기 및 Office 파일에 대한 풍부한 편집 환경을 통해 보다 최신 사용자 환경을 제공하여 LMS의 기존 Office 365 통합을 개선하고 있습니다. 또한 Microsoft는 앞으로 Microsoft OneDrive LTI 앱을 완전히 소유합니다. 즉, 항상 Microsoft에서 최신 및 가장 멋진 앱을 자동으로 다운로드할 수 있습니다.

Microsoft OneDrive LTI 앱을 사용하여 다음을 할 수 있습니다.

- Word 문서, PowerPoint 프레젠테이션 및 Excel을 비롯한 Office 365 파일을 리치 콘텐츠 편집기에서 첨부합니다.

- Office 365 클라우드 할당을 배포합니다.

- 개인 및 과정 Microsoft OneDrive 파일을 보고 구성합니다.

- 과정 구성원이 공유 문서에서 실시간으로 공동 작업할 수 있는 공동 작업을 만들 수 있습니다.

- 개인 및 학교 계정을 포함하여 여러 Microsoft OneDrive 계정에 액세스합니다.

- Office 365 파일을 과정 모듈과 통합합니다.

- LMS와의 Single Sign-On에 Microsoft 계정을 사용하세요.

## <a name="integrate-with-canvas"></a>Canvas와 통합

이 통합을 수행하는 사용자는 Canvas의 관리자이자 Microsoft 365 테넌트의 관리자입니다.

1. 테넌트 관리자 계정으로 Microsoft Azure Portal에 로그인합니다. Azure 테넌트 관리자에게도 그룹 관리자 역할이 있습니다.

    ![그룹 관리자가 강조 표시](../media/lti-media/lti-group-admin.png)

2. Microsoft [OneDrive LTI 포털에 로그인합니다.](https://odltiappnl.azurewebsites.net/admin)

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
    이는 Microsoft OneDrive LTI 포털의 클라이언트 ID 역할을 합니다.

5. Microsoft OneDrive LTI 포털의 클라이언트 **ID** 필드에 텍스트를 붙여넣고 다음 을 **선택합니다.**

6. **저장** 을 선택합니다.

7. LTI 테넌트 보기 를 선택하여 **설정을 확인합니다.**
