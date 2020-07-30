---
title: 조직에서 셀프 서비스 등록 사용
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_SMB
search.appverid:
- MET150
ms.assetid: 4f8712ff-9346-4c6c-bb63-a21ad7a62cbd
description: Microsoft 365 셀프 서비스에 제공 되는 microsoft Power Apps, Microsoft Flow 및 Dynamics 365 같은 금융 관련 셀프 서비스 프로그램에 대해 알아봅니다.
ms.openlocfilehash: 4a95c4b98821100d0a5164b87c1afe02b854608b
ms.sourcegitcommit: 6cf29958aff90d8bc1df0fe5fb9238d338db8237
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506300"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>조직에서 셀프 서비스 등록 사용

Microsoft에서 의견을 듣고 조직의 사용자가 마이크로소프트의 온라인 서비스에 쉽게 등록할 수 있도록 했습니다. 사용자는 구독에 의해 지불 되는 서비스를 사용 하도록 등록할 수 있고 대신 작업을 수행할 것을 요구 하지 않고 무료 서비스를 사용 하 여이 새로운 등록 프로세스 "셀프 서비스 등록"을 호출 합니다.
  
## <a name="how-self-service-sign-up-works"></a>셀프 서비스 등록 작동 방식

다음 예에서는 학교에서 자가 등록을 사용 하는 방법을 설명 합니다. 동일한 프로세스는 테 넌 트에서 셀프 서비스 프로그램이 사용 되도록 설정 된 모든 조직에 적용 됩니다.
  
1. 학생 및 교직원 구성원은 해당 조직과 연결 되었음을 나타내는 학교 전자 메일 주소를가지고 있습니다. 예를 들어 전자 메일 주소 jakob@uw.edu는 인천 대학교의 학생을 나타낼 수 있습니다.

2. 학생과 교사는 [웹 사이트로](https://go.microsoft.com/fwlink/p/?LinkId=536628)이동 하 고 전자 메일 주소를 사용 하 여 조직에서 제공 하는 서비스 (예: Microsoft 365 for Enterprise 용 앱)에 등록 합니다. 또한 제공 되는 다른 무료 서비스에 등록할 수도 있습니다.

3. 전자 메일 주소의 유효성을 검사 한 다음 Microsoft 365, Power BI 또는 기타 서비스 사용을 바로 시작할 수 있습니다.

4. 비즈니스 관리자는 관리 센터에서 **제품** 페이지를 보고 구독에 등록 한 사용자를 확인할 수 있습니다. 이 방법을 통해 테 넌 트의 서비스에 대해 새 라이선스 또는 인식할 수 없는 라이선스가 있는 경우를 확인할 수 있습니다. 사용자가 셀프 서비스 구독에 등록할 수 있는지 여부를 제어 하려면 **AllowAdHocSubscriptions** 매개 변수와 함께 [set-msolcompanysettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) PowerShell cmdlet을 사용 합니다. 자세한 내용은 [How to control services settings?](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/self-service-purchase-faq?view=o365-worldwide) 를 참조 하십시오.

## <a name="available-self-service-programs"></a>사용 가능한 셀프 서비스 프로그램

다음은 현재 사용할 수 있는 셀프 서비스 프로그램입니다. 이 목록은 새 프로그램을 추가할 때 업데이트 됩니다.
  
|||||
|:-----|:-----|:-----|:-----|
|**프로그램** <br/> |**설명** <br/> |**추가 정보** <br/> |셀프 서비스 등록 웹 사이트 * * * * <br/> |
|Office 365 A1 * * * * <br/> |학생 또는 교사는 학교 전자 메일 주소를 사용 하 여 무료 Office 365에 등록 하 고, 웹의 Office 앱, 1TB의 OneDrive 클라우드 저장소 및 SharePoint Online for a 수업용, 팀 및 프로젝트 사이트를 확인할 수 있습니다.  <br/> |[Office 365 교육 기술 FAQ](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |적격 학생 및 교사는 위의 모든 내용과 Microsoft 365 앱 for enterprise를 포함 하는 Office 365 A1 Plus에 등록할 수 있습니다. Microsoft 365 Business for enterprise는 데스크톱 또는 랩톱 컴퓨터에 설치 되어 있는 Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access 및 비즈니스용 Skype 등의 생산성 소프트웨어입니다.  <br/> |[Office 365 교육 기술 FAQ](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI에서는 사용자가 직관적인 새로운 방식으로 데이터를 시각화 하 고, 검색을 공유 하 고, 공동 작업을 수행할 수 있습니다. <br/> 조직에서 이미 구독을 신청한 경우 사용자에 게 고급 기능에 대 한 제한 된 무료 액세스 권한을 제공 하는 "Power BI Pro 개별 사용자 평가판"에 대 한 라이선스가 추가로 표시 될 수 있습니다.  <br/> |[조직의 Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536626) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**RMS(Rights Management Services)** <br/> |RMS for 개인이 azure RMS (azure 권한 관리)를 통해 보호 된 중요 한 파일을 보낸 조직의 사용자에 대 한 무료 셀프 서비스 구독 이지만 IT 부서가 azure RMS (Active Directory rights management Services) 또는 AD RMS를 구현 하지 않은 경우  <br/> |[개별 및 Azure 권한 관리를 위한 RMS](https://go.microsoft.com/fwlink/p/?LinkId=536627) <br/> |[Microsoft 권한 관리 포털](https://portal.azure.com/) -지정 된 권한으로 보호 된 문서를 열 수 있는지 여부를 확인할 수 있습니다.  <br/> |
|**Microsoft Power Apps** <br/> |PowerApps에서는 직접 만들었거나 다른 사람이 사용자와 함께 만들고 공유한 앱을 실행 하 여 조직 데이터를 관리할 수 있습니다. 앱은 휴대폰 등의 모바일 장치에서 실행 되거나 Dynamics 365를 열어 브라우저에서 실행할 수 있습니다. C #과 같은 프로그래밍 언어를 배워야 하지 않고 모두 무한 다양 한 앱을 만들 수 있습니다.  <br/> |[PowerApps에 대 한 셀프 서비스 등록](https://go.microsoft.com/fwlink/p/?linkid=841461) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Financials에 대 한 Dynamics 365** <br/> |중소 규모 기업을 위한 완전 한 비즈니스 및 재무 관리 솔루션을 확보 합니다. Financials의 Dynamics 365은 제 1 일부터 시작 하 여 주문, 판매, 송장 발부 및 보고 기능을 보다 쉽게 만듭니다.  <br/> |[Financials 용 Microsoft Dynamics 365](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Financials 용 Microsoft Dynamics 365](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**운영에 대 한 Microsoft Dynamics 365** <br/> |업무 속도를 높입니다. 운영에 대 한 Dynamics 365의 완전 한 ERP 도구는 속도를 향상 시키는 데 도움이 되는 글로벌 확장성 및 디지털 인텔리전스를 제공 합니다.  <br/> |[운영에 대 한 Microsoft Dynamics 365](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[운영에 대 한 Microsoft Dynamics 365](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource는 Microsoft 클라우드 플랫폼에 구축 된 소프트웨어 as-서비스 비즈니스 앱의 대상입니다. AppSource 기능은 Azure, Dynamics 365, Office 365 및 Power BI와 같은 Microsoft 제품의 기능을 확장 하는 수백 개의 앱, 추가 기능 및 콘텐츠 팩입니다.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Microsoft 파트너 성과급** <br/> |Microsoft 파트너 네트워크에는 세 가지 유형의 구성원 자격이 있습니다. 각 유형은 비즈니스가 성장 하는 데 도움이 되는 여러 가지 이점을 제공 합니다. 목표를 달성 함에 따라 사용자에 게 추가 혜택에 액세스 하 고 네트워크에서 us 및 기타 파트너와의 관계를 개발 하기 위한 고유한 요구에 적합 한 수준으로 프로그램에 참여 합니다.  <br/> |[Microsoft 파트너 성과급](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Microsoft 파트너 성과급](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft 비즈니스 센터** <br/> |Microsoft 비즈니스 센터는 Microsoft 제품 및 서비스 계약 (MPSA)을 통해 구매한 고객을 위한 포털입니다. <br/> |[빠른 시작: Microsoft 비즈니스 센터에 대 한 등록](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft 비즈니스 센터](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft 볼륨 라이선스 서비스 센터** <br/> |Microsoft 볼륨 라이선스 서비스 센터에는 Enterprise, Select, 교육부 (캠퍼스 또는 학교), 개방형 값, 오픈 라이선스 및 ISV 로열티 계약에 따라 구매한 라이선스가 표시 됩니다.  <br/> |[VLSC 교육 및 리소스](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[볼륨 라이선스 서비스 센터](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft 교육 에디션** <br/> |학습을 위한 플랫폼으로 Minecraft을 사용 하 여, 교육자는 모든 학생이 동기를 inspire 하 고 학습을 위한 열정을 ignite 수 있습니다. 교육 전문가 커뮤니티에 참여 Minecraft을 사용 하 여 학생의 잠재력을 해제 하는 방법을 알아봅니다.  <br/> |[Minecraft 교육 에디션](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft 교육 에디션](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |조직 전체에서 비디오를 업로드 하 고 공유 하 여 통신, 참여 및 학습을 개선 합니다.  <br/> |[&amp;하루 종일 알림 신청](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**전원 자동화** <br/> |전원 자동화는 즐겨 찾는 앱과 서비스 간에 자동화 된 워크플로를 설정 하 여 파일을 동기화 하 고, 알림을 가져오고, 데이터를 수집 하는 데 도움이 되는 제품입니다.  <br/> |[등록 및 로그인 하 여 전원 자동화](https://docs.microsoft.com/power-automate/sign-up-sign-in) <br/> |[전원 자동화](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**파워 가상 에이전트** <br/> |파워 가상 에이전트를 사용 하면 팀이 데이터 과학자 나 개발자 없이도 코딩 된 비 코드 그래픽 인터페이스를 통해 강력한 인공 지능을 쉽게 만들 수 있습니다. 파워 가상 에이전트는 현재 업계에서 bot 건물을 사용 하는 수많은 주요 문제를 해결 합니다. 이를 통해 주제별 전문가와 인공 지능 개발 팀 간의 차이와 문제점을 인식 하 고 문제를 해결 하기 위해 인공으로 업데이트 하는 팀 간의 긴 대기 시간을 없앨 수 있습니다.  <br/> |[라이선스 및 액세스 세부 정보](https://go.microsoft.com/fwlink/?linkid=2113708) <br/> |[파워 가상 에이전트 등록](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |Azure Active Directory (Azure AD) B2B (business to business) 공동 작업을 사용 하 여 외부 사용자 (또는 "게스트 사용자")를 유료 Azure AD services에 초대할 수 있습니다. 일부 기능은 무료로 제공 되지만 유료 Azure AD 기능에서는 사용자가 소유 하 고 있는 각 Azure AD edition 라이선스에 대해 최대 5 명의 게스트 사용자를 초대할 수 있습니다. <br/> |[Azure AD B2B 공동 작업 등록을 위한 셀프 서비스](https://docs.microsoft.com/azure/active-directory/b2b/self-service-portal) <br/> |[Azure Active Directory B2B 공동 작업 라이선스 지침](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) <br/> |