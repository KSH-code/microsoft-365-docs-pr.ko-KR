---
title: Microsoft 365 문제 및 권장 솔루션에 대한 통합만 지원
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: ServiceNow에 대한 범위가 지정한 인증된 응용 프로그램 설치 및 구성 가이드입니다.
ms.openlocfilehash: 427b4b20b33d83676e2cbebbfb6dcd627bcd51fe
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60661919"
---
# <a name="microsoft-365-support-integration-for-service-health-incidents-and-recommended-solutions-only"></a>Microsoft 365 문제 및 권장 솔루션에 대한 통합만 지원

이 구성에서는 ServiceNow 인스턴스를 통해 Microsoft 지원 서비스에서 사례를 만들 수 없습니다. 이 옵션은 ServiceNow 인스턴스를 통해 사용 가능한 서비스 상태 인시던트 정보 및 권장 솔루션만 제공합니다.

## <a name="prerequisites-service-health-incidents-and-recommended-solutions-only"></a>Prerequisites(서비스 상태 인시던트 및 권장 솔루션만)

이러한 필수 구성은 지원 통합 을 설정하는 **Microsoft 365 필요합니다.**

1. \[AAD 관리자 \] 테넌트 AAD 아웃바운드용 응용 프로그램을 Microsoft 365.

    1. 테넌트 자격 증명으로 Azure Portal에 Microsoft 365 등록 페이지에서 새 응용 [프로그램을 만드십시오.](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade)

    2. 이 조직 디렉터리에서만 **계정({Microsoft-365-tenant-name} 전용 - 단일** 테넌트)을 선택하고 등록을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

1. 인증으로 **이동하여** 플랫폼 **추가를 선택합니다.** 웹 옵션을 **선택하고** 리디렉션 URL을 입력합니다. `https://{your-servicenow-instance``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

1. 응용 프로그램 클라이언트 ID를 만들고 클라이언트 비밀을 만들고 해당 값을 얻습니다.

1. \[ServiceNow 관리자가 \] ServiceNow에서 아웃바운드 OAuth 공급자를 설정합니다.

    범위가 전역으로 설정되지 않은 경우 개발자 응용 프로그램 설정 **&gt; &gt; 전역으로** **전환합니다.** 

    :::image type="content" source="../../media/ServiceNow-guide/Servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/Servicenow-guide-image5.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 채팅 또는 문자 메시지 설명이 자동으로 생성됩니다.":::

1. 시스템 **OAuth &gt; 응용 프로그램 레지스트리로 이동하십시오.**

1. 타사 **OAuth** 공급자 커넥트 옵션을 사용하여 다음 값을 입력하여 새 응용 프로그램을 만들 수 있습니다.

    - 클라이언트 ID: 이 ID는 Prerequisites (Insights ONLY) 1단계에서 만든 응용 프로그램의 클라이언트 \# ID입니다.

    - 클라이언트 비밀: 이 값은 Prerequisites (Insights ONLY) 1단계에서 만든 응용 프로그램의 클라이언트 비밀 \# 값입니다.

    - 기본 부여 유형: 클라이언트 자격 증명

    - 토큰 URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - 리디렉션 URL: `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

## <a name="configure-the-microsoft-365-support-integration-application"></a>통합 Microsoft 365 응용 프로그램 구성

지원 Microsoft 365 통합 응용 프로그램은 지원에서 설정할 Microsoft 365 있습니다.

이러한 단계는 ServiceNow 인스턴스와 서비스 지원 서비스 간의 Microsoft 365 필요합니다.

1. \[ServiceNow 관리 \] 를 지원 **통합으로 Microsoft 365 전환합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="그래픽 사용자 인터페이스, 표 자동으로 생성되는 설명":::

1. \[ServiceNow 관리자 \] 지원 **Microsoft 365 &gt; 설정으로 이동하여** 통합 워크플로를 열 수 있습니다.

    > [!NOTE]
    > 표의 범위 간 액세스 정책으로 인해 \_ 'x \_ mioms \_ m365 assis'에서 'oauth 엔터티'에 대한 읽기 작업이 거부된 경우"라는 오류가 표시될 경우 테이블 액세스 정책에서 \_ 발생했습니다. 테이블 oauth **엔터티에 &gt;** 대해 모든 응용 프로그램 범위 읽기가 확인되어야 \_ 합니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image27.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image27.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

1. \[ServiceNow 관리자 \] **계속하려면 동의를** 선택합니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image11.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image11.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

1. \[ServiceNow 관리자가 \] 아웃바운드 OAuth 공급자를 설정합니다.

    아웃바운드 OAuth 공급자에 대한 OAuth 프로필을 선택하고 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image12.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image12.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

1. \[ServiceNow 관리자 \] 인바운드 OAuth 공급자를 건너뜁.

    현재 **단계 건너뛰기 를 선택하고** 다음 을 **선택합니다.**

1. \[ServiceNow 관리자 \] 인바운드 통화 통합 사용자를 건너뜁.

    현재 **단계 건너뛰기 를 선택하고** 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image34.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image34.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

1. \[ServiceNow 관리자가 \] 리포지토리 ID를 설정합니다.

    리포지토리 ID를 지정하고 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image15.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image15.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

1. \[ServiceNow 관리자 \] 응용 프로그램 설정 설정.

    이러한 설정을 선택하고 다음을 **선택합니다.**

    - SSO Microsoft 365: ServiceNow 인스턴스가 테넌트와 함께 SSO로 설정되어 있는지 Microsoft 365 확인하거나 선택을 선택하지 않습니다.

    - Microsoft 365 전자 메일: Microsoft 365 지원 사례가 만들어지면 연락을 받던 Microsoft 365 관리자 사용자의 전자 메일입니다.

    - 테스트 환경: Microsoft 지원 에이전트가 문제를 해결하기 위해 연락하지 않도록 테스트 단계를 나타내기 위해 확인란을 선택합니다. 지원 통합을 통해 공식적으로 Microsoft 365 상자의 확인란을 선택합니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image16.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image16.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

1. \[Microsoft 365 테넌트 관리자 \] 통합을 완료합니다.

    아래 정보가 올바른지 확인합니다. 이때 **다음을** 선택하지 않습니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image35.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image35.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

1. 조직 **Microsoft 365 관리 조직 &gt; 프로필 설정 &gt; 포털로 &gt; 이동합니다.**

1. 지원 통합 설정을 구성합니다.

    기본 정보 **탭>** **내부** 지원 도구 ServiceNow 를 선택하고 응용 프로그램 ID에 아웃바운드 앱 ID 값을 입력하여  >   **OAuth 토큰 필드를 발급합니다.**  이 아웃바운드 앱 ID는 6단계 – 통합 완료에 있습니다. 이 ID는 [Prerequisite (Insights ONLY) \# 1단계에서 생성되었습니다.](#prerequisites-service-health-incidents-and-recommended-solutions-only)

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

1. **리포지토리 탭에서** **리포지토리** 추가를 선택하여 다음 설정을 사용하여 새 리포지토리를 만들 수 있습니다.

    - 리포지토리: 6단계 - 통합 완료의 리포지토리 **ID** 값입니다.

    - 끝점:  6단계 - 통합 완료의 끝점 값입니다.

    - 인증 유형: 인증 **AAD 선택합니다.**

    - 클라이언트 ID: 임의 값(예: 무시)입니다.

    - Rest 사용자 이름: 임의 값(예: 무시)입니다.

    - Rest 사용자 암호: 임의 값(예: 무시)입니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image36.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image36.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

1. ServiceNow로 돌아갈 수 있습니다.

1. **다음을** 선택하여 통합을 완료합니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image37.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image37.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

1. \[ServiceNow 관리자 \] 기존 사용자에 대한 Microsoft 지원 통합을 사용하도록 설정

    Microsoft 365 지원 통합은 다음 역할 중 하나를 사용하는 사용자에 대해 사용하도록 설정됩니다.

    - x \_ mioms \_ m365 \_ assis.insights \_ 사용자

    - x \_ mioms \_ m365 \_ assis.administrator

    > [!NOTE]
    > 역할이 x \_ mioms \_ m365 assis.insights 사용자가 서비스 상태 인시던트, 권장 솔루션을 볼 \_ \_ 수 있습니다. 역할이 x \_ mioms \_ m365 assis.administrator인 사용자는 지원되는 사례를 Microsoft 365 \_ 있습니다. 이 Insights 경우 누구도 x \_ mioms \_ m365 \_ assis.administrator 역할을 할당할 수 없습니다.
