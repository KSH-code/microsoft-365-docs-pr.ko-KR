---
title: GDPR 및 CCPA에 대한 Visual Studio 제품군 데이터 주체 요청
description: GDPR 및 CCPA에 대한 Visual Studio 제품군 데이터 주체 요청
keywords: Visual Studio, Visual Studio Code, Mac용 Visual Studio, Visual Studio 설명서, 개인 정보, GDPR, CCPA
localization_priority: Priority
audience: itpro
ms.prod: visual-studio-family
ms.topic: article
ms.date: 05/24/2018
author: PoulChapman
ms.author: olholder
manager: pchapman
ms.collection:
- GDPR
- M365-security-compliance
ms.workload:
- multiple
ms.openlocfilehash: 96cb6820e24a378351c82264929c3aec99e6d4f6
ms.sourcegitcommit: 7713e777731025c165e9e936198609503ade5665
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "39624805"
---
# <a name="visual-studio-family-data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 및 CCPA에 대한 Visual Studio 제품군 데이터 주체 요청

EU [일반 데이터 보호 규정(GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm)은 사용자(규정에 _데이터 주체_로 알려짐)에게 개인 데이터를 관리할 수 있는 권리를 부여합니다. 개인 데이터는 GDPR에 따라 식별되거나 식별 가능한 자연인과 관련된 모든 데이터로 매우 광범위하게 정의됩니다. GDPR은 데이터 주체 특정 권한을 개인 데이터에 제공합니다. 이러한 권한에는 개인 데이터 복사본 획득, 수정 요청, 처리 제한, 삭제 또는 전자 형식으로 수신하는 권한이 포함됩니다. 해당 데이터 주체의 개인 데이터에 대해 조치를 취하는 데이터 컨트롤러(개인 데이터를 제어하는 고용주 또는 기타 유형의 에이전시 또는 조직)에 대한 데이터 주체의 공식 요청을 _데이터 주체 요청_ 또는 DSR이라고 합니다.

마찬가지로 캘리포니아 소비자 개인 정보 보호법(CCPA)은 캘리포니아 소비자에게 GDPR의 데이터 주체 권리와 유사한 권리를 포함하여, 소비자의 개인 정보 삭제, 액세스 및 수신(이식성)과 같은 개인 정보 보호 권리 및 의무를 제공합니다.  또한 CCPA는 특정 공개, 실행 권리 행사 시 차별 대우로부터 보호, “판매"로 분류되는 특정 데이터 전송에 대한 "옵트아웃(opt-out)/옵트인(opt-in)" 요구도 허용합니다. 판매는 가치 있는 대가관계를 위하여 데이터 공유를 포함하도록 광범위하게 정의됩니다. CCPA에 대한 자세한 내용은 [캘리포니아 소비자 개인 정보 보호법](offering-ccpa.md) 및 [캘리포니아 소비자 개인 정보 보호법 FAQ](ccpa-faq.md)를 참조하세요.

GDPR 대한 일반적인 내용은 [Service Trust portal의 GDPR 섹션](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)을 참조하세요.

## <a name="products-covered-by-this-guide"></a>이 가이드 적용을 받는 제품

이 가이드에서는 Microsoft 도구를 사용하여 인증(로그인)된 Visual Studio와 Mac용 Visual Studio, Microsoft 확장의 세션 사용 동안 수집된 개인 데이터를 이러한 항목 및 Visual Studio Code로 내보내거나 삭제하는 방법을 설명합니다. 이 가이드에서는 Visual Studio 개발자 커뮤니티, NuGet.org 및 ASP.NET 웹 사이트를 사용할 때 수집된 개인 데이터에 대해 데이터 주체 요청을 수행하는 방법도 설명합니다. 이러한 제품에서는 타사 도구 및 확장을 사용할 수 있으며, Microsoft가 이러한 도구 및 확장의 데이터 처리자 또는 관리자가 아닙니다. 사용자가 도구 또는 확장 공급자에게 문의하여 이러한 도구 및 확장에 대한 개인 데이터와 수집 정책을 파악해야 합니다.

## <a name="additional-privacy-information"></a>추가 개인 정보 보호 정보

제품과 함께 제공되는 Microsoft 소프트웨어 사용 조건, [Microsoft 개인정보취급방침](https://go.microsoft.com/fwlink/?LinkId=660726) 및 [Microsoft GDPR 약속](https://docs.microsoft.com/legal/gdpr)은 데이터 처리 규정을 설명합니다.

## <a name="visual-studio-visual-studio-for-mac-and-visual-studio-code"></a>Visual Studio, Mac용 Visual Studio, Visual Studio Code

### <a name="personal-data-we-collect"></a>수집한 개인 데이터

GDPR에 따른 데이터 프로세서로, Microsoft는 사용자가 Mac 및 Microsoft 확장용 Visual Studio 및 Visual Studio에 대한 경험을 제공하고 해당 Studio 및 Visual Studio Code를 향상하기 위해 필요한 데이터를 수집합니다. 데이터에는 고객 데이터와 시스템 생성 로그라는 두 가지 범주가 있습니다. 고객 데이터에는 이러한 제품이 제공하는 서비스를 수행하는 데 필요한 사용자 식별 가능한 트랜잭션 및 상호 작용 데이터가 포함됩니다. 예를 들어, 사용자에게 로밍 설정과 같은 개인화된 환경을 제공하려면 사용자 계정 정보 및 설정 데이터를 수집해야 합니다. 시스템 생성 로그는 문제를 식별하고 해결하며 제품과 서비스를 개선하는 데 사용되는 사용 또는 진단 데이터이며 사용자 이름과 같은 최종 사용자에 대한 식별 가능한 정보를 포함할 수 있습니다. 시스템 생성 로그는 18개월 동안 보관됩니다. 예를 들어, 시스템 생성 로그는 매일 제품 사용에 대해 집계되며 사용 날짜, 사용된 제품(예: "Visual Studio 2017"), 취한 조치(예: "vs/core/packagecostsummary/solutionload"), 조치가 취해진 횟수를 포함합니다.

```
{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/packagecostsummary/solutionload","Target":"1 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/ide/connected/accountmanagement/account","Target":"1 times",
"DevicePlatform": "Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{"Time":"2/27/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/perf/satellitepagefileusage","Target":"23 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}
```

자세한 내용은 [Visual Studio에서 수집된 시스템 생성 로그](https://docs.microsoft.com/visualstudio/ide/diagnostic-data-collection)를 참조하세요.

인증된 ID에 첨부된 개인 데이터만 DSR에서 처리할 수 있습니다. 예를 들어, Visual Studio Code는 로그인을 지원하지 않으므로 Visual Studio Code의 시스템 생성 로그를 인증된 ID에 첨부하지 않으면 처리할 수 없습니다. 하지만 Visual Studio Code에 대한 일부 Microsoft 확장은 인증된 데이터를 제공할 수 있으며 이 데이터는 DSR로 처리될 수 있습니다. 자세한 내용은 [GDPR 및 Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code)를 참조하세요. 일반적으로 Visual Studio 2013 이전 버전의 데이터는 저장하지 않습니다. 하지만 특정 확장 및 구성 요소는 인증된 ID에 첨부된 데이터를 제공할 수 있으며 아래에 설명된 대로 DSR에서 처리될 수 있습니다.

### <a name="how-users-can-control-personal-data"></a>사용자가 개인 데이터를 제어하는 방법

Visual Studio 2015 이상, Mac용 Visual Studio, Visual Studio Code는 사용자가 데이터 컬렉션을 중지하고 컨트롤러가 이미 수집한 데이터를 내보내거나 삭제할 수 있는 다음과 같은 방법을 제공합니다.

#### <a name="in-app-settings"></a>앱 내 설정

사용자는 이러한 제품의 개인 정보 설정을 제어할 수 있습니다. 자세한 내용은 다음을 참조하세요.

- [Visual Studio에서 개인 정보 설정을 관리하는 방법입니다](https://docs.microsoft.com/visualstudio/ide/visual-studio-experience-improvement-program).
- [Mac용 Visual Studio에서 개인 정보 설정을 관리하는 방법입니다](https://docs.microsoft.com/visualstudio/mac/visual-studio-experience-improvement-program).
- [Visual Studio Code에서 원격 분석 보고를 비활성화하는 방법입니다](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting).

#### <a name="exporting-or-deleting-data"></a>데이터 내보내기 또는 삭제

컨트롤러는 Visual Studio 제품군 또는 Microsoft 확장이 등록되는 방법에 따라 데이터 주체에서 수집한 사용자 지정 데이터 및 시스템 생성 로그를 두 가지 방법 중 하나로 관리할 수 있습니다. 경우에 따라 두 가지 방법을 모두 사용해야 합니다. 두 가지 방법 모두 컨트롤러가 해당 방법으로 관리되는 활동 기록의 복사본을 다운로드할 수 있습니다. AAD 또는 MSA 계정의 폐쇄는 관련 Visual Studio 사용자 지정 데이터를 삭제하고 이러한 제품과 관련된 시스템 생성 로그에서 개인 식별 가능한 데이터를 익명화합니다. 익명화된 시스템 생성 로그는 18개월 동안 보존됩니다.

- Azure 테넌트가 지원하는 계정(예를 들어, Azure 구독과 관련된 AAD 계정 또는 MSA 계정)을 사용하여 Visual Studio 제품군 제품을 등록한 사용자는 [GDPR에 대한 Azure 데이터 주체 요청](gdpr-dsr-azure.md)의 지침을 따를 수 있습니다.
- Azure 테넌트가 지원하는 계정 없이 Visual Studio 제품군 제품을 등록한 사용자(예: Microsoft 계정(MSA)을 사용하는 많은 계정)는 자신의 Microsoft 계정을 통해 사용할 수 있는 [웹 기반 Microsoft 개인 정보 보호 센터](https://aka.ms/userprivacysite)를 사용하여 여러 Microsoft 서비스 전반의 Microsoft 계정과 연결된 활동 데이터를 보고, 제어하고 삭제할 수 있습니다. 이 시나리오에서 사용자는 개인 데이터에 대한 관리자입니다.

> [!NOTE]
> MSA 계정 홀더가 자신의 계정을 삭제하면 Azure 테넌트가 계정을 지원했는지 여부에 상관없이 이들 제품과 관련된 모든 개인 식별 데이터가 삭제되고 시스템 생성 로그는 익명화됩니다.

Visual Studio 2013의 경우, 수집하는 데이터가 익명화됩니다. Visual Studio 2012 이전 릴리스의 경우, 데이터를 확인하는 즉시 삭제합니다. 두 경우 모두 나중에 보고 내보내거나 삭제할 항목이 없습니다.

## <a name="visual-studio-developer-community"></a>Visual Studio 개발자 커뮤니티

[개발자 커뮤니티](https://developercommunity.visualstudio.com) 웹사이트를 통한 [일반 데이터 보호 규정(GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) 요청을 지원합니다. 피드백 데이터를 보고 내보내거나 삭제할 수 있습니다.

### <a name="personal-data-we-collect"></a>수집한 개인 데이터

Microsoft는 사용자가 Visual Studio 제품군 제품에 대해 보고한 문제를 재현하고 해결하는 데 도움을 주는 데이터를 수집합니다. 개인 데이터에는 다음이 포함됩니다.

- [개발자 커뮤니티](https://developercommunity.visualstudio.com) 프로필 정보
- 기본 설정 및 알림
- [Visual Studio에 문제를 보고](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)하거나 [개발자 커뮤니티](https://developercommunity.visualstudio.com)를 통해 제공한 첨부 파일 및 시스템 생성 로그
- 투표

공개 피드백에는 문제, 메모, 솔루션이 포함됩니다.

### <a name="how-users-can-control-personal-data"></a>사용자가 개인 데이터를 제어하는 방법

#### <a name="view"></a>보기

피드백 관련 데이터를 보려면 다음 단계를 따릅니다.

1. [개발자 커뮤니티](https://developercommunity.visualstudio.com)에 로그인합니다. 오른쪽 상단 모서리에서 프로필을 클릭하고 **프로필 및 환경 설정**을 선택합니다.
2. **프로필**, **알림**, **활동** 및 **첨부 파일** 탭 중 하나를 클릭하면 피드백 시스템에 제출된 데이터를 볼 수 있습니다.
   1. **프로필**은 사용자 이름, 전자 메일 주소, 정보 등이 포함된 [개발자 커뮤니티](https://developercommunity.visualstudio.com)를 나타냅니다.
   2. **알림은 받은 전자 메일 알림을 제어하는 방법입니다.
   3. **활동**은 활동 중인(게시 및 메모 포함 등) 피드백 항목 및 수행한 활동을 제공합니다.
   4. **첨부 파일**은 `FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM`과 같은 형식의 첨부 파일 기록 목록입니다.

#### <a name="export"></a>내보내기

피드백 데이터를 DSR의 일부로 내보낼 수 있습니다. 다음을 포함하는 하나 이상의 .zip 보관함을 만듭니다.

- [개발자 커뮤니티](https://developercommunity.visualstudio.com) 프로필 정보
- 기본 설정 및 알림 설정
- [Visual Studio에 문제를 보고](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)하거나 [개발자 커뮤니티](https://developercommunity.visualstudio.com)를 통해 제공한 첨부 파일

> [!NOTE]
> 보관함에서 제공한 설명, 솔루션, 보고된 문제 등 공개 피드백은 제외됩니다.

내보내기를 시작하려면 다음 단계를 따릅니다.

1. [개발자 커뮤니티](https://developercommunity.visualstudio.com)에 로그인합니다. 오른쪽 상단 모서리에서 프로필을 클릭하고 **프로필 및 환경 설정**을 선택합니다.
2. **개인 정보 보호** 탭을 클릭하고** 보관함 만들기**를 클릭하여 데이터 내보내기를 요청합니다.
3. **보관함 상태**가 업데이트되어 데이터 준비 중임을 나타냅니다. 데이터를 사용할 수 있게 되기까지 시간은 내보내려는 데이터 양에 따라 다릅니다.
4. 데이터가 준비되면 전자 메일이 수신됩니다.
5. 전자 메일에서 **다운로드 보관함**을 클릭하거나 개인 정보 보호 탭으로 돌아가서 데이터를 다운로드합니다.

> [!NOTE]
> - 알림 탭에서 알림을 받지 않기로 선택한 경우 전자 메일을 보내지 않습니다.
> - 다시 내보내기를 요청하면 기존 보관함을 제거하고 새로운 보관함을 만듭니다.

#### <a name="delete"></a>삭제

삭제하면 [개발자 커뮤니티](https://developercommunity.visualstudio.com)에서 다음 사용자 정보가 제거됩니다.

- 프로필 정보
- 기본 설정 및 알림 설정
- [Visual Studio에 문제를 보고](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)하거나 [개발자 커뮤니티](https://developercommunity.visualstudio.com)를 통해 제공한 첨부 파일
- 투표

> [!NOTE]
> 귀하는 설명, 솔루션, 보고한 문제 등의 공개 정보는 삭제되지 않지만 익명화됩니다.
>
> [!IMPORTANT]
> AAD 또는 MSA 계정을 삭제하면 [개발자 커뮤니티](https://developercommunity.visualstudio.com)의 삭제 프로세스가 트리거됩니다.

삭제를 시작하려면 다음 단계를 따릅니다.

1. [개발자 커뮤니티](https://developercommunity.visualstudio.com)에 로그인합니다. 오른쪽 상단 모서리에서 프로필을 클릭하고 **프로필 및 환경 설정**을 선택합니다.
2. **개인 정보 보호** 탭을 클릭한 다음 **데이터 및 계정 삭제**를 클릭하여 데이터 삭제를 시작합니다.
3. 확인 화면이 나타납니다.
4. 상자에 “삭제”를 입력하고 **내 계정 삭제**를 클릭합니다.

**내 계정 삭제:** 를 클릭하면

- 사용자가 로그아웃됩니다.
- [개발자 커뮤니티](https://developercommunity.visualstudio.com) 계정, 개인 데이터, 첨부 파일을 삭제합니다.
- 사용자의 공개 피드백을 익명화합니다. 공개 피드백은 개발자 커뮤니티에서 사용할 수 있으며 익명 사용자가 신고한 것으로 표시됩니다.
- 계정이 삭제되면 더 이상 시스템에 존재하지 않으므로 전자 메일이 전송되지 않습니다. 
- 새 문제를 보고하거나 [개발자 커뮤니티](https://developercommunity.visualstudio.com)에 로그인하면 새 사용자로 식별됩니다.
- [개발자 커뮤니티](https://developercommunity.visualstudio.com)에서 계정을 삭제하면 다른 Microsoft 서비스에서 계정을 삭제하지 않습니다.

## <a name="xamarin-forums"></a>Xamarin 포럼

### <a name="personal-data-we-collect"></a>수집한 개인 데이터

[Xamarin 포럼](https://forums.xamarin.com/) 사용자 커뮤니티를 통해 Microsoft에서 사용자가 제공하는 데이터를 수집하여 사용자에게 발생한 Microsoft 제품 및 서비스 관련 문제를 재현하고 해결하는 데 도움을 얻을 수 있습니다. 이 데이터에는 개인 데이터와 공개 피드백이 포함됩니다. 수집하는 개인 데이터는 사용자 계정 데이터(예: Xamarin 포럼에 연결된 사용자 이름 및 전자 메일 주소)이며, 수집하는 공개 피드백에는 Xamarin 포럼을 통해 사용자가 제공하는 버그, 문제, 메모 및 솔루션이 포함되어 있습니다.

### <a name="how-you-can-control-your-data"></a>데이터를 제어하는 방법

#### <a name="xamarin-forums"></a>Xamarin 포럼

##### <a name="view"></a>보기

활성 Xamarin 포럼 계정이 있는 사용자는 Xamarin 포럼 계정 페이지에서 개인 데이터와 공개 피드백(예: 게시한 스레드 및 포스트 전부)을 볼 수 있습니다. 사용자는 계정 페이지를 통해 개인 데이터를 편집할 수도 있습니다.

##### <a name="export"></a>내보내기

Xamarin 포럼은 타사, Vanilla 포럼에 의해 호스트됩니다. 공개 데이터 내보내기를 요청하려면 사용자는 forums@xamarin.com(Xamarin 팀에서 모니터링함)에 문의해야 합니다. 그러면 Vanilla 포럼과 직접 작업하여 이 요청을 처리하게 됩니다.

##### <a name="delete"></a>삭제

Xamarin 포럼은 타사, Vanilla 포럼에 의해 호스트됩니다. 개인 및 공개 데이터의 삭제를 요청하려면 사용자는 forums@xamarin.com(Xamarin 팀에서 모니터링함)에 문의해야 합니다. 그러면 사용자의 개인 데이터 삭제 요청을 직접 처리합니다.

> [!NOTE]
> Xamarin용 Bugzilla는 더 이상 새 문제를 수락하지 않습니다. 이전 Xamarin Bugzilla 계정 소유자는 보고한 모든 버그의 보관 파일과 [https://xamarin.github.io/bugzilla-archives/](https://xamarin.github.io/bugzilla-archives/)에서 버그에 추가한 모든 메모를 볼 수 있습니다. 보관 파일에 포함된 개인 데이터를 삭제하도록 요청하려면 사용자는 [https://github.com/xamarin/bugzilla-archives/issues/new/choose](https://github.com/xamarin/bugzilla-archives/issues/new/choose)에 제출 및 발행할 수 있습니다. 사용자가 Xamarin Bugzilla에 게시한 공개 피드백(예: 버그, 문제, 메모 및 솔루션)은 삭제 요청을 받은 후에는 삭제되지 않습니다. 대신에 삭제 요청을 제출한 사용자가 만든 공개 피드백과 연관된 이름 및 전자 메일 주소를 제거하여 공개 피드백을 익명화할 수 있습니다.

## <a name="nuget"></a>NuGet

NuGet에 대한 DSR의 자세한 내용은 [NuGet 사용자 데이터 요청](https://docs.microsoft.com/nuget/policies/data-requests)을 참조하세요.

## <a name="aspnet"></a>ASP.NET

ASP.NET 웹사이트에 대한 DSR의 자세한 내용은 [ASP.NET 웹사이트 및 GDPR 데이터 주체 요청 처리](https://www.asp.net/gdpr)를 참조하세요.

## <a name="iisnet"></a>IIS.NET

IIS.NET 웹사이트에 대한 DSR의 자세한 내용은 [IIS.NET 웹사이트 및 GDPR 데이터 주체 요청 처리](https://www.iis.net/gdpr)를 참조하세요.

## <a name="other-visual-studio-family-services"></a>기타 Visual Studio 제품군 서비스

### <a name="surveymonkey"></a>SurveyMonkey

때때로 고객들을 초대하여 SurverMonkey를 통해 이러한 제품들에 대한 피드백을 제공하도록 합니다. 이 데이터는 28일 이내에 삭제됩니다. 이러한 제품에 대한 데이터 주체 요청을 처리할 때 인증된 설문 조사 응답이 있는 경우 데이터 주체 요청을 내보내고 삭제할 때 이를 포함합니다.

## <a name="learn-more"></a>자세한 정보

- [일반적으로 사용할 수 있는 엔터프라이즈 소프트웨어 제품의 고객에 대한 Microsoft의 GDPR 약속](https://docs.microsoft.com/legal/gdpr)
- [Microsoft 보안 센터](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [서비스 보안 포털](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [Microsoft 개인 정보 대시보드](https://account.microsoft.com/privacy)
- [Microsoft 개인 정보 응답 센터](https://aka.ms/userprivacysite)
- [GDPR에 대한 Azure 데이터 주체 요청](gdpr-dsr-azure.md)
