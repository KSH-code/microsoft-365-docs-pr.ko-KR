---
title: ServiceNow 구성 가이드와 Microsoft 365 지원 통합
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
ms.openlocfilehash: 58b955509fd998e7478ad32704c00bd89d692098
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60171990"
---
# <a name="microsoft-365-support-integration-with-servicenow-configuration-guide"></a>ServiceNow 구성 가이드와 Microsoft 365 지원 통합

[개요](#overview) 

[ServiceNow 환경의 응용 프로그램 종속성](#application-dependencies-in-servicenow-environments)

[구성 지침](#configuration-instructions)

[Who 지원 통합을 Microsoft 365 수 있나요?](#who-can-set-up-microsoft-365-support-integration)

[통합 지원에서 사용할 수 있는 Microsoft 365 기능은 무엇입니까?](#what-features-are-available-in-microsoft-365-support-integration) 

[ServiceNow Microsoft 365 통합 지원 설정](#set-up-microsoft-365-support-integration-with-servicenow-basic-authentication)

[AAD Microsoft 365 통합 지원 설정](#set-up-microsoft-365-support-integration-with-aad-oauth-token)

[전용에 Microsoft 365 지원 통합 Insights 설정](#set-up-microsoft-365-support-integration-for-insights-only) 

[구성 테스트](#testing-the-configuration) 

[문제 해결](#troubleshooting) 

## <a name="overview"></a>개요

Microsoft 365 통합을 통해 Microsoft 365, 지원 및 서비스 상태와 ServiceNow를 통합할 수 있습니다. Microsoft의 알려진 문제 및 보고된 문제를 조사하고, 인시던트 문제를 해결하고, Microsoft 권장 솔루션을 사용하여 작업을 완료하고, 필요한 경우 Microsoft 휴먼 지원으로 에스컬레이터할 수 있습니다.

## <a name="application-dependencies-in-servicenow-environments"></a>ServiceNow 환경의 응용 프로그램 종속성

필요한 사용 권한:

- oauth \_ 엔터티

- oauth \_ 엔터티 \_ 프로필

지원 Microsoft 365 통합을 설치한 후 두 개의 응용 프로그램 범위 간 액세스가 만들어졌습니다. 어떤 이유로든 성공적으로 만들어지지 않은 경우 수동으로 만들어야 합니다.

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image1.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

## <a name="configuration-instructions"></a>구성 지침

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image2.png" alt-text="다이어그램 설명이 자동으로 생성됩니다.":::

지원 통합을 Microsoft 365 설정:

- 아웃바운드 및 Microsoft Azure Active Directory API 호출의 인증을 위해 AAD(응용 프로그램을 AAD)에 등록합니다.

- 아웃바운드 및 인바운드 데이터 흐름 모두에 대해 Microsoft AAD 응용 프로그램을 사용하여 ServiceNow 엔터티를 만들 수 있습니다.

- 서비스 포털을 통해 ServiceNow 인스턴스를 Microsoft Microsoft 365 관리 통합합니다.

## <a name="who-can-set-up-microsoft-365-support-integration"></a>Who 지원 통합을 Microsoft 365 수 있나요?

- AAD 응용 프로그램을 만들 수 있는 권한이 있는 모든 사용자

- ServiceNow 관리자.

- 테넌트의 헬프데스크 관리자 또는 Microsoft 365 요청 관리자입니다.

## <a name="what-features-are-available-in-microsoft-365-support-integration"></a>통합 지원에서 사용할 수 있는 Microsoft 365 기능은 무엇입니까?

Microsoft 365 통합을 위한 구성을 설정하기 전에 다음 질문에 대한 답변을 검토하세요.

**질문 #1** ServiceNow 환경에서 인바운드 웹 서비스 호출에 대해 기본 인증(ServiceNow 사용자 자격 증명으로 액세스)을 허용하나요?

**질문 #2** 테넌트가 여러 개인 경우 서비스 지원 통합을 위해 ServiceNow 환경과 통합된 단일 테넌 Microsoft 365 계획입니까?

위의 질문에 대한 답변에 따라 다음 표에는 사용 가능한 기능과 지원 통합을 설정하는 Microsoft 365 설명되어 있습니다. 각 기능에 대한 설명은 Microsoft 365 [통합을 참조하세요.](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f)

|질문 #1 답변|질문 #2 답변|사용할 수 있는 기능은 무엇입니까?|구성 단계|
|--- |--- |--- |--- |
|예|예|서비스 상태 인시던트 <br/>권장 솔루션 </br>Microsoft 서비스 요청|[ServiceNow Microsoft 365 통합 지원 설정](#set-up-microsoft-365-support-integration-with-servicenow-basic-authentication)|
|예|아니요|서비스 상태 인시던트 <br/>권장 솔루션 </br>Microsoft 서비스 요청||
|아니요|예|서비스 상태 인시던트 <br/>권장 솔루션 </br>Microsoft 서비스 요청|[AAD Microsoft 365 통합 지원 설정](#set-up-microsoft-365-support-integration-with-aad-oauth-token)|
|아니요|아니요|서비스 상태 인시던트 <br/>권장 솔루션|[전용에 Microsoft 365 지원 통합 Insights 설정](#set-up-microsoft-365-support-integration-for-insights-only) |

## <a name="set-up-microsoft-365-support-integration-with-servicenow-basic-authentication"></a>ServiceNow Microsoft 365 통합 지원 설정

### <a name="prerequisites-basic-authentication"></a>Prerequisites(기본 인증)

지원 통합을 설정하는 데 일부 필수 Microsoft 365 필요합니다.

1. \[AAD 응용 프로그램을 만들 수 있는 사용자 테넌트에서 \] AAD 응용 프로그램을 Microsoft 365.

    1. 테넌트 자격 증명으로 [Azure Portal에](https://portal.azure.com/) Microsoft 365 로그온합니다.

    1. 앱 등록 페이지로 이동하여 새 응용 프로그램을 만드십시오.

        이 **조직 디렉터리에서만 계정({microsoft-365-tenant-name} 전용 – 단일 테넌트)을 선택합니다.**

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image3.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

    1. 리디렉션 URL 추가: `https://{your-servicenow-instance}.service-now.com/oauth_redirect.do` .

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image4.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

    1. 응용 프로그램 클라이언트 ID를 다운로드하고 앱 비밀을 생성합니다.

2. \[ServiceNow 관리자인 사용자가 \] ServiceNow에서 아웃바운드 OAuth 공급자를 설정합니다.

    1. 범위가 전역으로 설정되지 않은 경우 개발자 응용 **설정**   >    >  **전역으로** 전환합니다. 

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 채팅 또는 문자 메시지 설명이 자동으로 생성됩니다.":::

    1. 시스템 **OAuth**  >  **응용 프로그램 레지스트리로 이동하십시오.**

    1. 타사 OAuth 공급자에 대한 커넥트 값을 사용하여 새 응용 프로그램을 **만드시다.**

    - 클라이언트 ID: 1단계에서 만든 응용 프로그램의 \# 클라이언트 ID

    - 클라이언트 비밀: 1단계에서 만든 응용 프로그램의 앱 \# 비밀

    - 기본 부여 유형: 클라이언트 자격 증명

    - 토큰 URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - 리디렉션 URL: `https://{service-now-instance-name}.service-now.com/auth_redirect.do`

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image6.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

3. \[ServiceNow 관리자인 사용자가 \] 인바운드 OAuth 공급자를 설정합니다.

    1. 범위가 전역으로 설정되지 않은 경우 개발자 응용 **설정**   >    >  **전역으로** 전환합니다. 

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

    1. 시스템 **OAuth**  >  **응용 프로그램 레지스트리로 이동하십시오.**

    1. 외부 클라이언트에 대한 **OAuth API 끝점** 만들기를 선택하여 새 응용 프로그램을 만들 수 있습니다. 인바운드 OAuth 공급자의 이름을 지정하고 다른 필드는 기본값으로 그대로 두면 됩니다.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image7.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

4. \[ServiceNow 관리자인 사용자 통합 \] 사용자 만들기

    통합 사용자를 지정해야 합니다. 기존 통합 사용자가 없는 경우 또는 이 통합에 대한 특정 사용자를 만들 경우 조직 사용자로 이동하여 새 사용자를  >   만들 수 있습니다.

    새 통합 사용자를 만드는 경우 웹 서비스 액세스만 **확인란을 선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image8.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

### <a name="optional-allow-the-services-ips-of-microsoft-365-support-integration"></a>\[선택적 지원 통합을 위해 서비스의 \] Microsoft 365 허용

회사에서 자체 정책을 사용하여 인터넷 액세스를 제한하는 경우 인바운드 및 아웃바운드 API 액세스에 대해 아래의 IP 주소를 Microsoft 365 지원 서비스에서 네트워크 액세스를 사용하도록 설정하세요.

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> 이 터미널 명령은 지원 통합을 위해 서비스의 Microsoft 365 나열합니다.`nslookup connector.rave.microsoft.com`

### <a name="set-up-microsoft-365-support-integration-application"></a>지원 Microsoft 365 응용 프로그램 설정

지원 Microsoft 365 통합 응용 프로그램은 지원에서 설정할 Microsoft 365 있습니다.

이러한 단계는 ServiceNow 인스턴스와 서비스 지원 서비스 간의 Microsoft 365 필요합니다.

1. \[ServiceNow 관리자인 사용자는 통합을 지원하기 위해 \] Microsoft 365 전환합니다.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image9.png" alt-text="그래픽 사용자 인터페이스, 표 자동으로 생성되는 설명":::

2. \[ServiceNow 관리자인 사용자는 통합 흐름을 \] Microsoft 365 > **지원으로** 이동하세요.

    > [!NOTE]
    > 표의 범위 간 액세스 정책으로 인해 \_ 'x \_ mioms \_ m365 assis'에서 'oauth 엔터티'에 대한 읽기 작업이 거부된 경우"라는 오류가 표시될 경우 테이블 액세스 정책에서 \_ 발생했습니다. 테이블 oauth **엔터티에** 대해 모든 응용 프로그램 범위 읽기가 확인되어야  >   \_ 합니다.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image10.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

3. \[ServiceNow 관리자인 사용자 \] 동의를 선택하여  동의합니다.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image11.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

4. \[ServiceNow 관리자인 사용자가 \] 아웃바운드 OAuth 공급자를 설정합니다.

    [Prerequisites(기본 인증)](#prerequisites-basic-authentication) 2단계에서 만든 아웃바운드 OAuth 공급자에 대한 OAuth 프로필을 선택하고 \# 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image12.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

5. \[ServiceNow 관리자인 사용자가 \] 인바운드 OAuth 공급자를 설정합니다.

    - 현재 단계 **건너뛰기(Skip current step)를 Uncheck(현재 단계 건너뛰기)**

    - 외부 **OIDC Auth 토큰 을(를)스킹하지 않습니다.**

    - [Prerequisites(기본 인증)](#prerequisites-basic-authentication) 3단계에서 만든 OAuth 클라이언트를 선택하고 \# 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image13.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

6. \[ServiceNow 관리자인 사용자 \] 인바운드 통화 통합 사용자를 설정합니다.

    - 현재 단계 **건너뛰기(Skip current step)를 Uncheck(현재 단계 건너뛰기)**

    - [Prerequisites(기본 인증)](#prerequisites-basic-authentication) 4단계에서 만든 통합 사용자를 선택하고 \# 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image14.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

7. \[ServiceNow 관리자인 사용자가 \] 리포지토리 ID를 설정합니다.

    리포지토리 ID를 지정하고 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image15.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

8. \[ServiceNow 관리자인 사용자 응용 프로그램 \] 설정

    다음 설정을 선택하고 다음 을 **선택합니다.**

    - SSO Microsoft 365: ServiceNow 인스턴스가 테넌트와 함께 SSO로 설정되어 있는지 Microsoft 365 확인하거나 선택을 선택하지 않습니다.

    - Microsoft 365 전자 메일: Microsoft 365 지원 사례가 만들어지면 연락을 받던 Microsoft 365 관리자 사용자의 전자 메일입니다.

    - 테스트 환경: Microsoft 지원 에이전트가 문제를 해결하기 위해 연락하지 않도록 테스트 단계를 나타내기 위해 확인란을 선택합니다. 지원 통합을 통해 공식적으로 Microsoft 365 상자의 확인란을 선택합니다.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image16.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

9. \[테넌트의 기술 지원 Microsoft 365 서비스 요청 \] 관리자입니다.

    1. 아래 정보를 확인하여 올바른지 확인합니다.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image17.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

    1. 조직 설정 Microsoft 365 [관리](https://admin.microsoft.com/)포털 설정 로  >    >    >  **이동합니다.**

    1. 지원 통합 설정 설정:

        1. 기본 **정보 탭에서** 지금 내부 지원 도구 **서비스** 시작을 선택하고, [Prerequisites(기본 인증)](#prerequisites-basic-authentication) 1단계에서 만든 Step - 6 Complete 페이지에서 응용 프로그램 ID 값으로 아웃바운드 앱 **ID를** 입력합니다. \#

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image18.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

        1. **리포지토리** 탭에서 **리포지토리** 추가를 선택하여 다음 설정을 사용하여 새 리포지토리를 만들 수 있습니다.

            - 리포지토리: Step - 6 Complete the integration(통합 완료) 페이지의 리포지토리 **ID** 값입니다.

            - 끝점: **Step** - 6 Complete the integration(6단계 통합 완료) 페이지의 끝점 값입니다.

            - 인증 유형: **기본 인증을 선택합니다.**

            - 클라이언트 ID: Step - 6 Complete the integration(6단계 통합 완료) 페이지의 클라이언트 **ID** 값입니다.

            - 클라이언트 암호: [Prerequisites(기본 인증)](#prerequisites-basic-authentication) 3단계에서 만든 인바운드 OAuth 공급자의 \# 비밀입니다.

            - 새로 고침 토큰 만료: 864000

            - Rest username: The **User Name** value from page Step - 6 Complete the integration.

            - Rest user password: [Prerequisites(기본 인증)](#prerequisites-basic-authentication) 4단계에서 만든 통합 사용자의 \# 암호입니다.

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image19.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성":::

        1. 돌아가서 단추를 선택하여 통합을 저장합니다.

    1. **다음을** 선택하여 통합을 완료합니다.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image20.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램, 웹 사이트 설명이 자동으로 생성됩니다.":::

10. \[ServiceNow 관리자인 사용자는 기존 \] Microsoft 365 통합을 지원할 수 있습니다.

    Microsoft 365 지원 통합은 다음 역할 중 하나를 사용하는 사용자에 한해 사용하도록 설정됩니다.

    - x \_ mioms \_ m365 \_ assis.insights \_ 사용자

    - x \_ mioms \_ m365 \_ assis.administrator

    > [!NOTE]
    > 역할이 x \_ mioms \_ m365 \_ assis.insights 사용자 역할인 사용자는 서비스 상태 인시던트, 권장 솔루션을 볼 \_ 수 있습니다. 역할이 x \_ mioms \_ m365 assis.administrator인 사용자는 지원되는 사례를 Microsoft 365 \_ 있습니다.

11. \[선택적 \] \[ 역할이 있는 x_mioms_m365_assis.administrator \] Link Microsoft 365 관리 계정입니다.

    x \_ mioms \_ m365 assis.administrator 역할이 있으며 다른 Microsoft 365 계정을 사용하여 Microsoft 365 지원 사례를 관리하는 사용자는 Microsoft 365 지원 > 링크 계정으로 이동하여 Microsoft 365 관리자 전자 메일을 \_ 설정해야 합니다.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image21.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

## <a name="set-up-microsoft-365-support-integration-with-aad-oauth-token"></a>AAD Microsoft 365 통합 지원 설정

### <a name="prerequisites-aad-oauth-token"></a>Prerequisites(AAD OAuth Token)

이러한 필수 구성 단계는 지원 통합을 설정하는 Microsoft 365 필요합니다.

1. \[AAD 응용 프로그램을 만들 수 있는 사용자 테넌트 아래에 \] 아웃바운드용 AAD 응용 프로그램을 Microsoft 365 있습니다.

    1. 테넌트 자격 [증명을](https://portal.azure.com/) Microsoft 365 Azure Portal에 로그온합니다.

    1. 앱 등록 **페이지로 이동하여** 새 응용 프로그램을 만드십시오.

        이 **조직 디렉터리에서만 계정({microsoft-365-tenant-name} 전용 – 단일 테넌트)을 선택합니다.**

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image3.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

    1. 리디렉션 URL 추가: `https://{your-servicenow-instance}.service-now.com/auth_redirect.do` .

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image4.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

    1. 응용 프로그램의 클라이언트 ID를 다운로드하고 앱 비밀을 생성합니다.

2. \[AAD 응용 프로그램을 만들 수 있는 사용자 테넌트 아래에 \] Rest용 AAD 응용 프로그램 Microsoft 365 있습니다.

    1. 테넌트 자격 증명으로 [Azure Portal에](https://portal.azure.com/) Microsoft 365 로그온합니다.

    1. 앱 **등록으로 이동하여** 새 응용 프로그램을 생성합니다.

        이 **조직 디렉터리에서만 계정({microsoft-365-tenant-name} 전용 – 단일 테넌트)을 선택합니다.**

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image22.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

    1. 응용 프로그램 클라이언트 ID를 다운로드하고 앱 비밀을 생성합니다.

3. \[AAD 응용 프로그램을 만들 수 있는 사용자 테넌트 아래에 Rest \] User용 AAD 응용 Microsoft 365 있습니다.

    1. 테넌트 자격 증명으로 [Azure Portal에](https://portal.azure.com/) Microsoft 365 로그온합니다.

    1. 앱 등록 **페이지로 이동하여** 새 응용 프로그램을 만드십시오.
        
        이 **조직 디렉터리에서만 계정({microsoft-365-tenant-name} 전용 – 단일 테넌트)을 선택합니다.**

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

    1. 응용 프로그램 클라이언트 ID를 다운로드하고 앱 비밀을 생성합니다.

4. \[ServiceNow 관리자인 사용자가 \] ServiceNow에서 아웃바운드 OAuth 공급자를 설정합니다.

    1. 범위가 전역으로 설정되지 않은 경우 개발자 응용 **설정**   >    >  **전역으로** 전환합니다. 

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 채팅 또는 문자 메시지 설명이 자동으로 생성됩니다.":::

    1. 시스템 **OAuth**  >  **응용 프로그램 레지스트리로 이동하십시오.**

    1. 타사 OAuth 공급자에 대한 커넥트 값을 사용하여 새 응용 프로그램을 **만드세요.**

        - 클라이언트 ID: [AAD OAuth 토큰(Prerequisites)](#prerequisites-aad-oauth-token) 1단계에서 만든 응용 프로그램의 클라이언트 \# ID입니다.

        - 클라이언트 비밀: [AAD OAuth 토큰(Prerequisites)](#prerequisites-aad-oauth-token) 1단계에서 만든 응용 프로그램의 앱 \# 비밀입니다.

        - 기본 부여 유형: 클라이언트 자격 증명.

        - 토큰 URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

        - 리디렉션 URL: `https://{service-now-instance-name}.service-now.com/auth_redirect.do`

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image6.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

5. \[ServiceNow 관리자 ServiceNow에서 OIDC 공급자를 구성하는 사용자는 온라인 \] 설명서 를 [참조하십시오.](https://docs.servicenow.com/bundle/quebec-platform-administration/page/administer/security/task/add-OIDC-entity.html)

    1. 범위가 전역으로 설정되지 않은 경우 개발자 응용 **설정**   >    >  **전역으로** 전환합니다. 

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 채팅 또는 문자 메시지 설명이 자동으로 생성됩니다.":::

    1. 시스템 **OAuth**  >  **응용 프로그램 레지스트리로 이동하십시오.**

    1. 새로 **만들기 새**  >  **열기 ID 커넥트 공급자 를 선택합니다.**

    1. **OAuth OIDC 공급자** 구성에서 검색을 선택하고 다음 값을 사용하여 "oidc provider  \_ configuration.list"에서 새 OIDC 공급자 \_ 구성을 생성합니다.

        - OIDC 공급자: Contoso Azure

        - OIDC 메타데이터 URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/.well-known/openid-configuration`

        - UserClaim: **appId**

        - 사용자 필드: **사용자 ID**

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image24.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

    1. OIDC 공급자 구성을 선택하여 다음 값을 사용하여 **ID 토큰을** 확인하여 새 응용 프로그램을 만들 수 있습니다.

        - 이름: contoso \_ 응용 프로그램 \_ 인바운드 \_ api

        - 클라이언트 ID: [AAD OAuth 토큰(Prerequisites)](#prerequisites-aad-oauth-token) 2단계에서 만든 응용 프로그램의 클라이언트 \# ID입니다.

        - 클라이언트 비밀: [AAD OAuth 토큰(Prerequisites)](#prerequisites-aad-oauth-token) 2단계에서 만든 응용 프로그램의 앱 \# 비밀입니다.

        - OAuth OIDC 공급자 구성: 마지막 단계에서 만든 OIDC 공급자입니다.

        - 리디렉션 URL:  
            `https://{service-now-instance-name}.service-now.com/oauth_redirect.do`

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image25.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

6. \[ServiceNow 관리자인 사용자 \] 통합 사용자 만들기

    조직   >  **사용자로 이동하여** 통합 사용자가 없는 경우 새 사용자를 만들 수 있습니다. 사용자 **ID 값은** [Prerequisites(AAD OAuth Token)](#prerequisites-aad-oauth-token) 3단계에서 만든 응용 프로그램 클라이언트 \# ID입니다.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image26.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

### <a name="optional-allow-the-services-ips-of-microsoft-365-support-integration"></a>\[선택적 지원 통합을 위해 서비스의 \] Microsoft 365 허용

회사에서 자체 정책을 사용하여 인터넷 액세스를 제한하는 경우 인바운드 및 아웃바운드 API 액세스를 모두 허용하여 Microsoft 365 지원 서비스에 대한 네트워크 액세스를 사용하도록 설정하세요.

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> 이 터미널 명령은 *nslookup* 및 Microsoft 365 통합을 위한 서비스의 모든 활성 CONNECTOR.RAVE.MICROSOFT.COM

### <a name="set-up-microsoft-365-support-integration"></a>지원 Microsoft 365 설정

지원 Microsoft 365 통합 응용 프로그램은 설치 프로그램 지원의 설치 프로그램을 통해 **Microsoft 365** 있습니다.

이러한 단계는 ServiceNow 인스턴스와 서비스 지원 서비스 간의 통합을 Microsoft 365 필요합니다.

1. \[ServiceNow 관리자인 사용자는 통합을 지원하기 위해 \] Microsoft 365 전환합니다.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image9.png" alt-text="그래픽 사용자 인터페이스, 표 자동으로 생성되는 설명":::

2. \[ServiceNow 관리자인 사용자는 통합 흐름을 \] Microsoft 365 > **지원으로** 이동하세요.

    > [!NOTE]
    > 표의 범위 간 액세스 정책으로 인해 \_ 'x \_ mioms \_ m365 assis'에서 'oauth 엔터티'에 대한 읽기 작업이 거부된 경우"라는 오류가 표시될 경우 테이블 액세스 정책에서 \_ 발생했습니다. 테이블 oauth **엔터티에** 대해 모든 응용 프로그램 범위 읽기가 확인되어야  >   \_ 합니다.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image27.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

3. \[ServiceNow 관리자인 사용자는 동의를 선택하여 \] 동의합니다. 

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image11.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

4. \[ServiceNow 관리자인 사용자가 \] 아웃바운드 OAuth 공급자를 설정합니다.

    [Prerequisites (AAD OAuth Token)](#prerequisites-aad-oauth-token) 4단계에서 만든 아웃바운드 OAuth 공급자에 대한 OAuth 프로필을 선택하고 \# 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image12.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

5. \[ServiceNow 관리자인 사용자가 \] 인바운드 OAuth 공급자를 설정합니다.

    1. 현재 단계 **건너뛰기(Skip current step)를 Uncheck(현재 단계 건너뛰기)**

    1. 외부 **OIDC Auth 토큰을 검사합니다.**

    1. [Prerequisites (AAD OAuth Token)](#prerequisites-aad-oauth-token) 5단계에서 만든 OAuth 클라이언트를 선택하고 다음 을 **선택합니다.**

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image28.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

6. \[ServiceNow 관리자인 사용자가 \] 인바운드 통화 통합 사용자 설정

    1. 현재 단계 **건너뛰기(Skip current step)를 Uncheck(현재 단계 건너뛰기)**

    1. [Prerequisites(AAD OAuth Token)](#prerequisites-aad-oauth-token) 3단계에서 만든 응용 프로그램의 클라이언트 ID를 입력하고 다음 \# 을 **선택합니다.**

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image39.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

7. \[ServiceNow 관리자인 사용자가 \] 리포지토리 ID를 설정합니다.

    리포지토리 ID를 지정하고 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image15.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

8. \[ServiceNow 관리자인 사용자 응용 프로그램 설정 \] 설정.

    다음 설정을 선택하고 다음 을 **선택합니다.**

    - SSO Microsoft 365: ServiceNow 인스턴스가 테넌트와 함께 SSO로 설정되어 있는지 Microsoft 365 확인하거나 선택을 선택하지 않습니다.

    - Microsoft 365 전자 메일: Microsoft 365 지원 사례가 만들어지면 연락을 받던 Microsoft 365 관리자 사용자의 전자 메일입니다.

    - 테스트 환경: Microsoft 지원 에이전트가 문제를 해결하기 위해 연락하지 않도록 테스트 단계를 나타내기 위해 확인란을 선택합니다. 지원 통합을 통해 공식적으로 Microsoft 365 상자의 확인란을 선택합니다.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image16.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

    1. **다음** 을 선택합니다.

9. \[테넌트의 기술 지원 Microsoft 365 서비스 요청 \] 관리자입니다.

    1. 다음 정보를 확인하여 올바른지 확인합니다.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image40.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

    1. 조직 설정 Microsoft 365 [관리](https://admin.microsoft.com)포털 설정 로  >    >    >  **이동합니다.**

    1. 지원 통합 설정을 선택합니다.

        1. 기본  정보 탭에서  내부 지원 도구로 서비스 시작을 선택하고 1단계- 6단계 통합 [완료(AAD OAuth 토큰)](#prerequisites-aad-oauth-token) 1단계에서 만든 통합 완료 페이지에서 응용 프로그램 ID 값으로 아웃바운드 앱 **ID를** \# 입력합니다.

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image18.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

        1. **리포지토리 탭에서** **리포지토리** 추가를 선택하여 다음 정보를 사용하여 새 리포지토리를 만들 수 있습니다.

            - 리포지토리: 단계 - 6 통합 완료 페이지의 리포지토리 **ID** 값을 사용하세요.

            - 끝점:  Step - 6 Complete the integration page의 끝점 값입니다.

            - 인증 유형: **AAD 인증을 선택합니다.**

            - 클라이언트 ID: Step - 6 Complete the integration(통합 완료) 페이지의 클라이언트 **ID** 값으로, [Prerequisites(AAD OAuth Token)](#prerequisites-aad-oauth-token) 2단계에서 만든 응용 프로그램의 클라이언트 \# ID입니다.

            - Rest username: The **User Name value** on the Step - 6 Complete the integration page, which is the Client **ID** of the application created in [Prerequisites (AAD OAuth Token) step](#prerequisites-aad-oauth-token) \# 3.

            - Rest user password: The App Secret of the application created in [Prerequisites (AAD OAuth Token)](#prerequisites-aad-oauth-token) step \# 3.

                :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image31.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

        1. 돌아가서 단추를 선택하여 통합을 저장합니다.

    1. **다음을** 선택하여 통합을 완료합니다.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image32.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

10. \[ServiceNow 관리자인 사용자는 기존 \] Microsoft 365 통합을 지원할 수 있습니다.

    Microsoft 365 지원 통합은 다음 역할이 있는 사용자에 한해 사용하도록 설정됩니다.

    - x \_ mioms \_ m365 \_ assis.insights \_ 사용자

    - x \_ mioms \_ m365 \_ assis.administrator

    > [!NOTE]
    > 역할이 x \_ mioms \_ m365 assis.insights 사용자가 서비스 상태 인시던트, 권장 솔루션을 볼 \_ \_ 수 있습니다. 역할이 x \_ mioms \_ m365 assis.administrator인 사용자는 지원되는 사례를 Microsoft 365 \_ 있습니다.

11. **\[선택 \] \[ 사항 역할이 있는 x_mioms_m365_assis.administrator \] Link Microsoft 365 관리 계정**

    "x \_ mioms \_ m365 assis.administrator" 역할이 있는 사용자가 다른 Microsoft 365 계정을 사용하여 Microsoft 지원 사례를 관리하는 경우 Microsoft 365 지원 > 링크 계정으로 이동하여 Microsoft 365 관리자 전자 메일을 설정해야 \_ 합니다.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image21.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

## <a name="set-up-microsoft-365-support-integration-for-insights-only"></a>전용에 Microsoft 365 지원 통합 Insights 설정

### <a name="prerequisites-insights-only"></a>선행 준비(Insights 전용)

이러한 필수 구성 단계는 지원 통합을 설정하는 Microsoft 365 필요합니다.

1. \[AAD 응용 프로그램을 만들 수 있는 사용자 테넌트에서 \] AAD 응용 프로그램을 Microsoft 365.

    1. 테넌트 자격 증명으로 [Azure Portal에](https://portal.azure.com/) Microsoft 365 로그온합니다.

    1. 앱 등록 **페이지로 이동하여** 새 응용 프로그램을 만드십시오.

        이 **조직 디렉터리에서만 계정({microsoft-365-tenant-name} 전용 – 단일 테넌트)을 선택합니다.**

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image3.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

    1. 리디렉션 URL 추가: `https://{your-servicenow-instance}.service-now.com/auth_redirect.do`

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image4.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

    1. 응용 프로그램의 클라이언트 ID를 다운로드하고 앱 비밀을 생성합니다.

1. \[ServiceNow 관리자인 사용자가 \] ServiceNow에서 아웃바운드 OAuth 공급자를 설정합니다.

    1. 범위가 전역으로 설정되지 않은 경우 개발자 응용 **설정**   >    >  **전역으로** 전환합니다. 

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 채팅 또는 문자 메시지 설명이 자동으로 생성됩니다.":::

    1. 시스템 **OAuth**  >  **응용 프로그램 레지스트리로 이동하십시오.**

    1. 타사 OAuth 공급자에 대한 커넥트 값을 사용하여 새 응용 프로그램을 **만드세요.**

        - 클라이언트 ID:  [Prerequisites (Insights ONLY)](#prerequisites-insights-only) 1단계에서 만든 응용 프로그램의 클라이언트 \# ID입니다.

        - 클라이언트 비밀: [Prerequisites (Insights ONLY)](#prerequisites-insights-only) 1단계에서 만든 응용 프로그램의 앱 \# 비밀

        - 기본 부여 유형: 클라이언트 자격 증명

        - 토큰 URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

        - 리디렉션 URL: `https://{servicenow-instance-name}.service-now.com/oauth_redirect.do`

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image6.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

### <a name="set-up-microsoft-365-support-integration"></a>지원 Microsoft 365 설정

지원 Microsoft 365 통합 응용 프로그램은 설치 프로그램을  통해 설정할 Microsoft 365 있습니다.

ServiceNow 인스턴스와 Microsoft 지원 간의 통합을 설정하려면 다음 단계가 필요합니다.

1. \[ServiceNow 관리자인 사용자는 통합을 지원하기 위해 \] Microsoft 365 전환합니다.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image9.png" alt-text="그래픽 사용자 인터페이스, 표 자동으로 생성되는 설명":::

2. \[ServiceNow 관리자인 사용자는 통합 흐름을 \] Microsoft 365 > **지원으로** 이동하세요.

    > [!NOTE]
    > 표의 범위 간 액세스 정책으로 인해 \_ 'x \_ mioms \_ m365 assis'에서 'oauth 엔터티'에 대한 읽기 작업이 거부된 경우"라는 오류가 표시될 경우 테이블 액세스 정책에서 \_ 발생했습니다. 테이블 oauth **엔터티에** 대해 모든 응용 프로그램 범위 읽기가 확인되어야  >   \_ 합니다.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image27.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

3. \[ServiceNow 관리자인 사용자는 동의를 선택하여 \] 동의합니다. 

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image11.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

4. \[ServiceNow 관리자인 사용자가 \] 아웃바운드 OAuth 공급자를 설정합니다.

    아웃바운드 OAuth 공급자에 대한 OAuth 프로필을 선택하고 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image12.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

5. \[ServiceNow 관리자인 \] 사용자인 경우 인바운드 OAuth 공급자 건너뛰기.

    현재 **단계 건너뛰기 를 선택하고** 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image33.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

6. \[ServiceNow 관리자인 사용자는 \] 통합 사용자를 건너뜁합니다.

    현재 **단계 건너뛰기 를 선택하고** 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image34.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

7. \[ServiceNow 관리자인 사용자가 \] 리포지토리 ID를 설정합니다.

    리포지토리 ID를 지정하고 다음 을 **선택합니다.**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image15.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

8. \[ServiceNow 관리자인 사용자 응용 프로그램 설정 \] 설정.

    올바른 설정을 선택하고 다음 을 **선택합니다.**

    - SSO Microsoft 365: ServiceNow 인스턴스가 테넌트에서 SSO로 설정되어 있는지 Microsoft 365 합니다. 그렇지 않은 경우 이의를 확정하지 않습니다.

    - Microsoft 365 관리 전자 메일: Microsoft 365 지원 사례를 만들 때 연락할 Microsoft 365 관리자의 전자 메일입니다.

    - 테스트 환경: Microsoft 지원 에이전트가 문제를 해결하기 위해 연락하지 않도록 테스트 단계를 나타내기 위해 확인란을 선택합니다. 지원 통합을 통해 공식적으로 Microsoft 365 상자의 확인란을 선택합니다.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image16.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램 설명이 자동으로 생성됩니다.":::

9. \[테넌트의 기술 지원 Microsoft 365 서비스 요청 \] 관리자입니다.

    1. 여기에 있는 정보를 확인하여 올바른지 확인합니다.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image35.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

    1. 조직 설정 Microsoft 365 [관리](https://admin.microsoft.com)포털 설정 로  >    >    >  **이동합니다.**

        1. 설치 흐름에 표시된 정보와 지원 통합 설정을 합니다.

        1. 기본 **정보 탭에서**  지금 서비스를 내부 지원 도구로 선택하고 아웃바운드 앱 **ID를** 응용 프로그램 ID로 입력하여 OAuth 토큰을 발급합니다.

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image18.png" alt-text="그래픽 사용자 인터페이스, 텍스트, 응용 프로그램, 전자 메일 설명이 자동으로 생성됩니다.":::

        1. **리포지토리 탭에서** **리포지토리** 추가를 선택하여 다음 정보를 사용하여 새 리포지토리를 만들 수 있습니다.

            - 리포지토리: Step - 6 Complete the integration(통합 완료) 페이지의 리포지토리 **ID** 값입니다.

            - 끝점:  Step - 6 Complete the integration page의 끝점 값입니다.

            - 인증 유형: **AAD 인증을 선택합니다.**

            - 클라이언트 ID: 무시와 같은 임의 **값입니다.**

            - Rest 사용자 이름: 무시와 같은 임의의 **값입니다.**

            - Rest user password: a random value, such as **ignored**.

                :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image36.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

        1. 돌아가서 단추를 선택하여 통합을 저장합니다.

    1. **다음을** 선택하여 통합을 완료합니다.

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image37.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램 설명이 자동으로 생성됩니다.":::

10. \[ServiceNow 관리자인 사용자는 기존 \] Microsoft 365 통합을 지원할 수 있습니다.

    Microsoft 365 지원 통합은 다음 사용자 역할에만 사용하도록 설정됩니다.

    - x \_ mioms \_ m365 \_ assis.insights \_ 사용자

    - x \_ mioms \_ m365 \_ assis.administrator

    > [!NOTE] 
    > 역할이 x_mioms_m365_assis.insights_user는 서비스 상태 인시던트, 권장 솔루션을 볼 수 있습니다. 또한 x_mioms_m365_assis.administrator 역할이 있는 사용자는 지원이 없는 사례를 Microsoft 365 있습니다. 이 Insights.administrator 역할은 누구도 할당되지 x_mioms_m365_assis.

## <a name="testing-the-configuration"></a>구성 테스트

응용 프로그램에 외부 시스템과의 성공적인 통신이 필요한 경우 성공적인 구성을 위해 연결을 테스트하는 방법을 간략하게 설명하십시오.

지원 통합의 구성을 테스트하는 Microsoft 365 단계는 다음과 같습니다.

1. 관리자로 ServiceNow 포털에 로그온합니다.

2. 인시던트 열기

3. 지원 **Microsoft 365 탭에** 중점을 두고  Microsoft 365 Insights 해결 방법을 성공적으로 검색하는지 여부를 선택합니다.

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image38.png" alt-text="그래픽 사용자 인터페이스, 응용 프로그램, 웹 사이트 설명이 자동으로 생성됩니다.":::

##  <a name="troubleshooting"></a>문제 해결

|#|문제|진단 작업|
|--- |--- |--- |
|1|지원 탭에서 **Microsoft 365 수** 없습니다.|필터 필터가 **있는** 현재 보기 및 시스템 로그  >   x_mioms_m365_assit|
|2|**Microsoft 권장 해결 방법을 선택하지만** "ServiceNow 관리자에게 문의하여 앱의 설정 단계를 완료해달라"는 오류가 발생합니다.|양식의 맨 위에 있는 오류 메시지와 시스템 로그 필터가 있는 x_mioms_m365_assit  >  |
|3 |**Microsoft 권장 해결 방법을 선택하지만** "ServiceNow 관리자에게 문의하여 앱에 대한 최종 설정 단계를 완료해달라"는 오류가 발생합니다.|양식의 맨 위에 있는 오류 메시지와 시스템 로그 필터가 있는 x_mioms_m365_assit  >  |
|4 |검색 상자에 문제를 입력하고 Microsoft 권장 해결 방법을 **선택하지만** "ServiceNow 관리자에게 문의하여 앱의 설정 단계를 완료해달라"는 오류가 발생합니다.|양식의 맨 위에 있는 오류 메시지와 시스템 로그 필터가 있는 x_mioms_m365_assit  >  |
|5|검색 상자에 문제를 입력하고 **Microsoft** 권장 해결 방법을 선택하지만 "ServiceNow 관리자에게 문의하여 앱에 대한 최종 설정 단계를 완료해달라"는 오류가 발생합니다.|양식의 맨 위에 있는 오류 메시지와 시스템 로그 필터가 있는 x_mioms_m365_assit  >  |
|6 |Microsoft **고객 지원에 문의를** 선택하고 "ServiceNow 관리자에게 문의하여 앱의 설정 단계를 완료해달라"는 오류가 표시됩니다.|양식의 맨 위에 있는 오류 메시지와 시스템 로그 필터가 있는 x_mioms_m365_assit  >  |
|7 |Microsoft 지원 서비스에 **문의를** 선택하고 "ServiceNow 관리자에게 문의하여 앱에 대한 최종 설정 단계를 완료해달라"는 오류가 발생합니다.|양식의 맨 위에 있는 오류 메시지와 시스템 로그 필터가 있는 x_mioms_m365_assit  >  |
|8 |Microsoft **지원에 문의하지만** "{EmailAddress}가 유효한 관리자 계정이 Microsoft 365 않습니다. 서비스 Microsoft 365 열기 위해 관리자 권한이 필요합니다. 앱에서 관리자 계정을 연결합니다."|양식의 맨 위에 있는 오류 메시지와 시스템 로그 필터가 있는 x_mioms_m365_assit  >  |
|9 |**Microsoft 권장 솔루션을 선택하지만** 아무 것도 표시하지 않음|시스템 **로그 확인 – 필터** 로그 및 필터가 있는 아웃바운드 HTTP login.microsoftonline.com connector.rave.microsoft.com|
|10 |Microsoft **권장 솔루션을 선택하지만** "앱 지원에 문의하세요."라는 오류가 발생합니다.|양식의 맨 위에 있는 오류 메시지와 시스템 로그 필터가 있는 x_mioms_m365_assit  >  |
|11 |검색 상자에 문제를 입력하고 **Microsoft** 권장 해결 방법 선택하지만 아무 것도 표시하지 않음|시스템 **로그 확인 – 필터** 로그 및 필터가 있는 아웃바운드 HTTP login.microsoftonline.com connector.rave.microsoft.com|
|12 |검색 상자에 문제를 입력하고 Microsoft 권장 솔루션을 **선택하지만** "앱 지원에 문의하세요."라는 오류가 표시됩니다.|양식의 맨 위에 있는 오류 메시지와 시스템 로그 필터가 있는 x_mioms_m365_assit  >  |
|13|사용자가 **Microsoft 지원에 문의를 선택했지만** 아무 것도 일어나지 않습니다.|시스템 **로그 확인 – 필터** 로그 및 필터가 있는 아웃바운드 HTTP login.microsoftonline.com connector.rave.microsoft.com|
|14 |인시던트 다시 열고 Microsoft 권장 솔루션을 볼 수 없습니다.|필터 **로그가 있는** 시스템 로그  >   x_mioms_m365_assit|
|15 |Microsoft 지원으로 전송된 인시던트 다시 열 때 Microsoft 사례를 볼 수 없습니다.|필터 **로그가 있는** 시스템 로그  >   x_mioms_m365_assit|
|16 |티켓 세부 정보를 저장할 수 없습니다. "티켓 세부 정보를 저장할 수 없습니다. 앱 지원에 문의하세요."|양식 맨 위에 있는 오류 메시지 확인|
