---
title: ServiceNow 기본 인증과의 지원 통합 구성
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
ms.openlocfilehash: 4aefd0afa21b3fbb80aa318fbac7b30cf374d924
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60701336"
---
# <a name="configure-support-integration-with-servicenow-basic-authentication"></a>ServiceNow 기본 인증과의 지원 통합 구성

## <a name="prerequisites-basic-authentication"></a>Prerequisites(기본 인증)

이러한 필수 구성은 지원 통합 을 설정하는 **Microsoft 365 필요합니다.**

1. \[AAD 관리자 \] 테넌트 AAD 응용 프로그램을 Microsoft 365.

    1. 테넌트 자격 증명으로 azure Portal에 Microsoft 365 로그인하고 앱 [](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade) 등록 페이지로 이동하여 새 응용 프로그램을 만드십시오.

    1. 이 조직 디렉터리에서만 **계정({Microsoft-365-tenant-name} 전용 – 단일** 테넌트)을 선택하고 등록을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

1. 인증으로 **이동하여** 플랫폼 **추가를 선택합니다.** 웹 옵션을 **선택하고** 리디렉션 URL을 입력합니다. `https://{your-servicenow-instance``}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

1. 응용 프로그램 클라이언트 ID를 만들고 클라이언트 비밀을 만들고 해당 값을 얻습니다.

1. \[ServiceNow 관리자가 \] ServiceNow에서 아웃바운드 OAuth 공급자를 설정합니다.

    범위가 전역으로 설정되지 않은 경우 개발자 응용 프로그램 설정 **&gt; &gt; 전역으로** **전환합니다.** 

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 채팅 또는 문자 메시지 설명이 자동으로 생성됩니다.":::

1. 시스템 **OAuth &gt; 응용 프로그램 레지스트리로 이동하십시오.**

1. 타사 **OAuth** 공급자 커넥트 옵션을 사용하여 다음 값을 입력하여 새 응용 프로그램을 만들 수 있습니다.

    - 클라이언트 ID: 1단계에서 만든 응용 프로그램의 클라이언트 \# ID입니다.

    - 클라이언트 비밀: 1단계에서 만든 응용 프로그램의 클라이언트 비밀 \# 값입니다.

    - 기본 부여 유형: 클라이언트 자격 증명

    - 토큰 URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - 리디렉션 URL: `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

1. \[ServiceNow 관리자가 \] 인바운드 OAuth 공급자를 설정합니다.

    범위가 **전역으로** 설정되지 않은 경우 개발자 응용 프로그램으로 설정 **&gt; 전역으로 &gt;** **전환합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 채팅 또는 문자 메시지 설명이 자동으로 생성됩니다.":::

1. 시스템 **OAuth &gt; 응용 프로그램 레지스트리로 이동하십시오.**

1. 외부 클라이언트에 대한 **OAuth API** 끝점 만들기 옵션을 사용하여 새 응용 프로그램을 만들 수 있습니다. 인바운드 OAuth 공급자의 이름을 지정하고 다른 모든 필드는 기본값으로 그대로 두면 됩니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image7.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image7.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

1. \[ServiceNow 관리자 \] 통합 사용자를 생성합니다.

    통합 사용자를 지정해야 합니다. 기존 통합 사용자가 없는 경우 또는 이 통합에 대해 특별히 만들어야 하는 **&gt;** 경우 조직 사용자로 이동하여 새 사용자를 만들 수 있습니다.

    새 통합 사용자를 만드는 경우 웹 서비스 액세스만 **옵션을** 선택합니다. 또한 이 사용자에게 인시던트 관리자 역할을 **\_ 부여해야** 합니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image8.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image8.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

## <a name="optional-allow-the-services-ip-addresses-to-microsoft-365-support-integration"></a>\[OPTIONAL 서비스 IP 주소가 지원 통합을 \] 지원할 Microsoft 365 허용

회사에서 자체 정책을 사용하여 인터넷 액세스를 제한하는 경우 인바운드 및 아웃바운드 API 액세스에 대해 아래의 IP 주소를 허용하여 Microsoft 365 지원 서비스에 대한 네트워크 액세스를 사용하도록 설정하세요.

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> 이 터미널 명령은 지원 통합을 위해 서비스의 Microsoft 365 나열합니다.`nslookup`` connector.rave.microsoft.com`

## <a name="configure-the-microsoft-365-support-integration-application"></a>통합 Microsoft 365 응용 프로그램 구성

지원 Microsoft 365 통합 응용 프로그램은 지원에서 설정할 Microsoft 365 있습니다.

이러한 단계는 ServiceNow 인스턴스와 서비스 지원 서비스 간의 Microsoft 365 필요합니다.

1. \[ServiceNow 관리 \] 를 지원 **통합으로 Microsoft 365 전환합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="그래픽 사용자 인터페이스, 표 자동으로 생성되는 설명":::

1. \[ServiceNow 관리자 \] 지원 **Microsoft 365 &gt; 설정으로 이동하여** 통합 워크플로를 열 수 있습니다.

    > [!NOTE]
    > 표의 범위 간 액세스 정책으로 인해 \_ 'x \_ mioms \_ m365 assis'에서 'oauth 엔터티'에 대한 읽기 작업이 거부된 경우"라는 오류가 표시될 경우 테이블 액세스 정책에서 \_ 발생했습니다. 테이블 oauth **엔터티에 &gt;** 대해 모든 응용 프로그램 범위 읽기가 확인되어야 \_ 합니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image10.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image10.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

1. \[ServiceNow 관리자 \] **계속하려면 동의를** 선택합니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image11.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image11.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

1. \[ServiceNow 관리자가 \] 아웃바운드 OAuth 공급자를 설정합니다.

    [Prerequisites(기본 인증) \# 2단계에서](#prerequisites-basic-authentication) 만든 아웃바운드 OAuth 공급자에 대한 OAuth 프로필을 선택하고 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image12.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image12.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

1. \[ServiceNow 관리자가 \] 인바운드 OAuth 공급자를 설정합니다.

    1. 현재 단계 **건너뛰기(Skip current step)를 Uncheck(현재 단계 건너뛰기)**

    1. 외부 **OIDC Auth 토큰 을(를)스킹하지 않습니다.**

    1. [Prerequisite (Basic Authentication) step \# 3에서](#prerequisites-basic-authentication)만든 OAuth 클라이언트를 선택하고 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image13.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image13.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

1. \[ServiceNow 관리자가 \] 인바운드 통화 통합 사용자를 설정합니다.

    1. 현재 단계 **건너뛰기(Skip current step)를 Uncheck(현재 단계 건너뛰기)**

    1. [Prerequisites (Basic Authentication) step \# 4에서](#prerequisites-basic-authentication)만든 통합 사용자를 선택하고 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image14.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image14.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

1. \[ServiceNow 관리자가 \] 리포지토리 ID를 설정합니다.

    리포지토리 ID를 지정하고 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image15.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image15.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

1. \[ServiceNow 관리자 \] 응용 프로그램 설정

    다음 설정을 선택하고 다음 을 **선택합니다.**

    - SSO Microsoft 365: ServiceNow 인스턴스가 테넌트와 함께 SSO로 설정되어 있는지 Microsoft 365 확인하거나 선택을 선택하지 않습니다.

    - Microsoft 365 전자 메일: Microsoft 365 지원 사례가 만들어지면 연락을 받던 Microsoft 365 관리자 사용자의 전자 메일입니다.

    - 테스트 환경: Microsoft 지원 에이전트가 문제를 해결하기 위해 연락하지 않도록 테스트 단계를 나타내기 위해 확인란을 선택합니다. 지원 통합을 통해 공식적으로 Microsoft 365 상자의 확인란을 선택합니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image16.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image16.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

1. \[Microsoft 365 테넌트 관리자 \] 통합을 완료합니다.

    아래 정보가 올바른지 확인합니다. 이때 **다음을** 선택하지 않습니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image17.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image17.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

1. 조직 **Microsoft 365 관리 조직 &gt; 프로필 설정 &gt; 포털로 &gt; 이동합니다.**

1. 지원 통합 설정을 구성합니다.

    기본 정보 **탭>** **내부** 지원 도구 ServiceNow 를 선택하고 응용 프로그램 ID에 아웃바운드 앱 ID 값을 입력하여  >   **OAuth 토큰 필드를 발급합니다.**  이 아웃바운드 앱 ID는 [Prerequisite (Basic Authentication) \# 1단계에서](#prerequisites-basic-authentication)만든 6단계 - 통합 완료에 있습니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

1. **리포지토리 탭에서** **리포지토리** 추가를 선택하여 다음 설정을 사용하여 새 리포지토리를 만들 수 있습니다.

    - 리포지토리: 6단계 - 통합 완료의 리포지토리 **ID** 값입니다.

    - 끝점:  6단계 - 통합 완료의 끝점 값입니다.

    - 인증 유형: **기본 인증을 선택합니다.**

    - 클라이언트 ID: **6단계** - 통합 완료의 클라이언트 ID 값입니다.

    - 클라이언트 암호: Prerequisites(기본 인증) 3단계에서 만든 인바운드 OAuth 공급자의 \# 비밀입니다.

    - 새로 고침 토큰 만료: 864000

    - Rest username: The **User Name** value from Step 6 – Complete the Integration.

    - Rest user password: [Prerequisites (Basic Authentication) step \# 4](#prerequisites-basic-authentication)에서 만든 통합 사용자의 암호입니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image19.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image19.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성":::

1. ServiceNow로 돌아갈 수 있습니다.

1. **다음을** 선택하여 통합을 완료합니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image20.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image20.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램, 웹 사이트 설명이 자동으로 생성됩니다.":::

1. \[ServiceNow 관리자 \] 기존 사용자에 대한 Microsoft 지원 통합을 사용하도록 설정

    Microsoft 365 지원 통합은 다음 역할 중 하나를 사용하는 사용자에 대해 사용하도록 설정됩니다.

    - x \_ mioms \_ m365 \_ assis.insights \_ 사용자

    - x \_ mioms \_ m365 \_ assis.administrator

    > [!NOTE]
    > 역할이 x \_ mioms \_ m365 \_ assis.insights 사용자 역할인 사용자는 서비스 상태 인시던트, 권장 솔루션을 볼 \_ 수 있습니다. 역할이 x \_ mioms \_ m365 assis.administrator인 사용자는 지원되는 사례를 Microsoft 365 \_ 있습니다.

1. \[OPTIONAL \] \[ 역할 x \_ mioms \_ m365 \_ assis.administrator 링크가 있는 Microsoft 365 관리 \] 계정입니다.

    x \_ mioms \_ m365 assis.administrator 역할이 있으며 다른 Microsoft 365 계정을 사용하여 Microsoft 365 지원 사례를 관리하는 사용자는 Microsoft 365 지원 링크 계정으로 이동하여 Microsoft 365 관리자 전자 \_ &gt; 메일을 설정해야 합니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image21.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image21.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::
