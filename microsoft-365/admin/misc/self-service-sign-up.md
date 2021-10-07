---
title: 조직에서 셀프 서비스 등록 사용
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: seemg, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_signup
search.appverid: MET150
description: Power Apps Microsoft Microsoft 365, Microsoft Power Automate 및 Dynamics 365 for Finance와 같은 셀프 서비스 등록 및 사용 가능한 셀프 서비스 프로그램에 대해 자세히 알아보습니다.
ms.date: 03/17/2021
ms.openlocfilehash: 87f432be0659d03a1e8f77b682997dc32d1dc111
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192694"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>조직에서 셀프 서비스 등록 사용

셀프 서비스 등록을 사용하면 조직의 사용자가 Microsoft의 온라인 서비스에 쉽게 등록할 수 있습니다. 이 등록 프로세스를 "셀프 서비스 등록"이라고 합니다. 사용자가 구독에서 결제한 서비스를 사용하기 위해 등록하거나, 사용자를 대신하여 작업을 수행하지 않고 무료 서비스를 사용할 수 있기 때문에 이 프로세스를 "셀프 서비스 등록"이라고 합니다.

## <a name="how-self-service-sign-up-works"></a>셀프 서비스 등록 작동 방식

다음 예제에서는 학교에서 셀프 등록이 작동하는 방식에 대해 설명합니다. 테넌트에서 셀프 서비스 프로그램이 활성화된 조직에는 동일한 프로세스가 작동합니다.

1. 학생 및 교직원에게는 해당 기관과 연관된 학교 전자 메일 주소가 있습니다. 예를 들어 전자 메일 jakob@uw.edu 워싱턴 대학의 학생을 나타낼 수 있습니다.
2. 학생과 교직원은 웹 사이트로 이동하여 전자 메일 주소를 사용하여 조직에서 제공하는 서비스(예: 사이트)에 엔터프라이즈용 Microsoft 365 앱. [](https://go.microsoft.com/fwlink/p/?LinkId=536628) 또한 서비스에서 제공하는 다른 무료 서비스에 등록할 수도 있습니다.
3. 전자 메일 주소의 유효성을 검사한 후 바로 Microsoft 365, Power BI 서비스를 사용할 수 있습니다.
4. 비즈니스 관리자는 라이선스 페이지의 라이선스 페이지에서 구독을 선택하여 구독에 등록한  Microsoft 365 관리 센터. 이렇게 하면 테넌트에 서비스에 대한 새 라이선스 또는 인식할 수 없는 라이선스가 있는 경우를 볼 수 있습니다. 사용자가 셀프 서비스 구독에 등록할 수 있는지 여부를 제어하려면 **AllowAdHocSubscriptions** 매개 변수와 함께 [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings) PowerShell cmdlet을 사용합니다. 자세한 내용은 [셀프 서비스 설정을 제어하는 방법을 참조하세요.](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>사용 가능한 셀프 서비스 프로그램

다음은 현재 사용 가능한 셀프 서비스 프로그램입니다. 이 목록은 새 프로그램이 추가될 때 업데이트됩니다.

| 프로그램 <br/> | 설명 <br/> | 추가 정보 <br/> | 셀프 서비스 등록 웹 사이트 <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 A1**** <br/> |학생 또는 교사는 학교 전자 메일 주소를 사용하여 무료 Office 365 등록하고 웹용 Office 앱, 수업, 팀 및 프로젝트 사이트의 경우 OneDrive 클라우드 저장소 SharePoint Online을 다운로드할 수 있습니다.  <br/> |[Office 365 Education 기술 FAQ](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |적격 학생 및 교사는 위에 언급된 모든 내용과 함께 Office 365 A1 Plus에 등록할 수 엔터프라이즈용 Microsoft 365 앱. 엔터프라이즈용 Microsoft 365 앱 Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access 및 비즈니스용 Skype 등의 생산성 소프트웨어입니다.  <br/> |[Office 365 Education 기술 FAQ](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI 통해 사용자는 직관적인 새로운 방식으로 데이터를 시각화하고, 검색을 공유하고, 공동 작업을 할 수 있습니다. <br/> 조직에서 이미 구독한 경우 사용자에게 고급 기능에 대한 제한적인 무료 액세스를 제공하는 "Power BI Pro 개별 사용자 평가판"에 대한 라이선스를 추가로 볼 수 있습니다.  <br/> |[Power BI 조직의 사용자 관리](./power-bi-in-your-organization.md) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**RMS(Rights Management Services)** <br/> |개인용 RMS는 Azure RMS(Azure 권한 관리)에서 보호된 중요한 파일을 전송했지만 IT 부서에서 Azure RMS(Azure 권한 관리) 또는 AD RMS(Active Directory Rights Management Services)를 구현하지 않은 조직의 사용자를 위한 무료 셀프 서비스 구독입니다.  <br/> |[개인용 RMS 및 Azure 권한 관리](/azure/information-protection/rms-for-individuals) <br/> |[권한으로 보호된](https://portal.azure.com/) 특정 문서를 열 수 있는지 여부를 확인할 수 있는 Microsoft 권한 관리 포털입니다.  <br/> |
|**Microsoft Power Apps** <br/> |이 Power Apps 만들거나 다른 사람이 생성하고 공유한 앱을 실행하여 조직 데이터를 관리할 수 있습니다. 앱은 휴대폰과 같은 모바일 장치에서 실행되거나 Dynamics 365를 열고 브라우저에서 실행할 수 있습니다. 앱과 같은 프로그래밍 언어를 학습하지 않고도 무한한 다양한 앱을 C#.  <br/> |[셀프 서비스 등록 Power Apps](/powerapps/maker/signup-for-powerapps) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |중소기업을 위한 완벽한 비즈니스 및 재무 관리 솔루션을 얻습니다. Dynamics 365 for Financials를 사용하면 첫 날부터 주문, 판매, 인보이스 및 보고를 보다 쉽게 할 수 있습니다.  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |비즈니스 수행 속도를 향상합니다. Dynamics 365 for Operations의 전체 ERP 도구는 글로벌 확장성 및 디지털 인텔리전스를 제공하여 속도에 따라 성장하는 데 도움이 됩니다.  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource는 Microsoft 클라우드 플랫폼을 사용하여 구축된 소프트웨어 as-a-service 비즈니스 앱의 대상입니다. AppSource는 Azure, Dynamics 365, Office 365 및 앱과 같은 Microsoft 제품의 기능을 확장하는 수백 개의 앱, 추가 기능 및 콘텐츠 팩을 Power BI.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Microsoft 파트너 인센티브** <br/> |Microsoft 파트너 네트워크는 세 가지 유형의 멤버십을 제공합니다. 각 유형은 비즈니스 성장에 도움이 되는 혜택 집합을 제공합니다. 목표를 달성할 때 더 많은 혜택에 액세스하고 네트워크의 다른 파트너와 관계를 구축하기 위해 고유한 요구 사항에 맞는 수준의 프로그램에 참여하세요.  <br/> |[Microsoft 파트너 인센티브](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Microsoft 파트너 인센티브](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft 비즈니스 센터** <br/> |Microsoft 비즈니스 센터는 MPSA(Microsoft 제품 및 서비스 계약)를 통해 구매한 고객을 위한 포털입니다. <br/> |[빠른 시작: Microsoft 비즈니스 센터에 등록](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft 비즈니스 센터](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft 볼륨 라이선스 서비스 센터** <br/> |Microsoft 볼륨 라이선스 서비스 센터에는 선택, 교육(캠퍼스 또는 Enterprise), Open Value, Open License 및 ISV 로열티 계약에 따라 구입한 라이선스가 표시됩니다.  <br/> |[VLSC 교육 및 리소스](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[볼륨 라이선스 서비스 센터](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |교사는 Minecraft 플랫폼으로 사용하여 모든 학생에게 더 많은 성과를 거는 동기를 부여하고 영감을 주며 학습에 대한 열정을 불어넣을 수 있습니다. 교육자 커뮤니티에 참여하여 학생 잠재력을 Minecraft 방법을 학습합니다.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |업로드, 참여 및 학습을 개선하기 위해 조직 전체에서 비디오를 공유하고 관리합니다.  <br/> |[&amp;0일 환경 등록](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |Power Automate 파일을 동기화하고, 알림을 받고, 데이터를 수집하는 등 즐겨 사용하는 앱과 서비스 간에 자동화된 워크플로를 설정하는 데 도움이 되는 제품입니다.  <br/> |[등록하고 로그인하여 Power Automate](/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**파워 가상 에이전트** <br/> |Power Virtual Agents 팀이 데이터 보호나 개발자 없이도 코드 없는 안내 그래픽 인터페이스를 사용하여 강력한 봇을 쉽게 만들 수 있도록 합니다. Power Virtual Agents 업계에서 봇을 구축할 때의 많은 주요 문제를 해결합니다. 주제 전문가와 봇을 구축하는 개발 팀 간의 간격과 문제를 인식하고 봇을 업데이트하여 문제를 해결하기 위해 봇을 업데이트하는 팀 간의 긴 대기 시간을 제거합니다.  <br/> |[라이선스 및 액세스 세부 정보](/power-virtual-agents/requirements-licensing) <br/> |[등록을 Power Virtual Agents](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |Azure Active Directory(Azure AD) B2B(Business-to-Business) 공동 작업을 통해 유료 Azure AD 서비스를 사용하기 위해 외부 사용자(또는 "게스트 사용자")를 초대할 수 있습니다. 일부 기능은 무료이지만 유료 Azure AD 기능의 경우 직원 또는 테넌트의 게스트가 아닌 사용자에 대해 소유한 각 Azure AD 버전 라이선스에 대해 최대 5개의 게스트 사용자를 초대할 수 있습니다. <br/> |[Azure AD B2B 공동 작업 등록을 위한 셀프 서비스](/azure/active-directory/b2b/self-service-portal) <br/> |[Azure Active Directory B2B 공동 작업 라이선싱 지침](/azure/active-directory/b2b/licensing-guidance) <br/> |
