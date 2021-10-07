---
title: Microsoft 클라우드 아키텍처 모델 - 엔터프라이즈 리소스 계획
description: 다음 Microsoft 클라우드 아키텍처 포스터는 Azure 및 클라우드와 같은 Microsoft 클라우드 서비스에 대한 정보를 Office 365.
ms.author: samanro
author: samanro
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: f7d663dc403d3323bf1dd1fa0ba210c26433cee1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210356"
---
# <a name="microsoft-cloud-for-it-architects-illustrations"></a>IT 설계자용 Microsoft 클라우드 그림

이러한 클라우드 아키텍처 포스터는 Microsoft 365, Azure Active Directory(Azure AD), Microsoft Intune, Microsoft Dynamics 365 및 하이브리드 사내 및 클라우드 솔루션을 비롯한 Microsoft 클라우드 서비스에 대한 정보를 제공합니다. 

IT 의사 결정권자 및 설계자는 이러한 리소스를 사용하여 워크로드에 이상적인 솔루션을 결정하고 네트워킹, ID 및 보안과 같은 핵심 인프라 구성 요소에 대한 의사 결정을 내릴 수 있습니다.

<a name="attacks"></a>
### <a name="common-attacks-and-microsoft-capabilities-that-protect-your-organization"></a>일반적인 공격 및 조직을 보호하는 Microsoft 기능
가장 일반적인 사이버 공격과 Microsoft가 모든 공격 단계에서 조직을 지원하는 방식을 자세히 알아봅니다. 

| 항목 | 설명 |
|:-----|:-----|
|[![일반적인 공격 포스터 그림. ](../media/solutions-architecture-center/common-attacks-model-thumb.png) ](https://download.microsoft.com/download/F/A/C/FACFC1E9-FA35-4DF1-943C-8D4237B4275B/MSFT_Cloud_architecture_security_commonattacks.pdf) <br/> [PDF](https://download.microsoft.com/download/F/A/C/FACFC1E9-FA35-4DF1-943C-8D4237B4275B/MSFT_Cloud_architecture_security_commonattacks.pdf) \| [Visio](https://download.microsoft.com/download/F/A/C/FACFC1E9-FA35-4DF1-943C-8D4237B4275B/MSFT_Cloud_architecture_security_commonattacks.vsdx) <br/> 2021년 9월에 업데이트되었습니다. | 이 포스터에서는 일반적인 공격의 경로를 보여 주고, 각 공격 단계에서 공격자를 중지하는 데 도움이 되는 기능에 대해 설명합니다. <br/><br/>**관련 솔루션 가이드** <br/> <ul><li>[평가 및 파일럿 Microsoft 365 Defender](../security/defender/eval-overview.md)</li><li>[권장 ID 및 장치 액세스 구성](../security/office-365-security/microsoft-365-policies-configurations.md)</li><li>[데이터 개인 정보 보호 규정에 대한 정보 보호를 Microsoft 365](information-protection-deploy.md)</li><li>[Microsoft 365 테넌트용 랜섬웨어 보호 배포](ransomware-protection-microsoft-365.md)</li><li>[Microsoft 365의 참가자 위험 솔루션](../compliance/insider-risk-solution-overview.md)</li></ul>

<a name="identity"></a>
### <a name="microsoft-cloud-identity-for-it-architects"></a>IT 설계자용 Microsoft 클라우드 ID

Microsoft 클라우드 서비스 및 플랫폼을 사용하는 조직용으로 ID를 설계하는 과정과 관련하여 IT 설계자가 파악해야 하는 사항
  
| 항목 | 설명 |
|:-----|:-----|
|[![Microsoft 클라우드 ID 모델의 축소판 이미지입니다.](../media/solutions-architecture-center/msft-cloud-identity-model-thumb.png)](../downloads/MSFT_cloud_architecture_identity.pdf) <br/> [PDF로 보기](../downloads/MSFT_cloud_architecture_identity.pdf) \| [PDF로 다운로드](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity.pdf)  <br/>2020년 9월에 업데이트되었습니다. | 이 모델에는 다음이 포함됩니다.  <ul> <li> Microsoft 클라우드를 사용하는 ID 소개 </li><li> Azure AD IDaaS 기능 </li><li> Azure AD와 AD DS(Active Directory 도메인 서비스) 계정 통합 </li><li> Azure IaaS에 디렉터리 구성 요소 추가 </li><li> Azure IaaS의 워크로드에 대한 AD DS 옵션 </li></ul><br/>  <br/>|

<a name="security"></a>
### <a name="microsoft-cloud-security-for-it-architects"></a>IT 설계자용 Microsoft 클라우드 보안

Microsoft 클라우드 서비스 및 플랫폼의 보안과 관련하여 IT 설계자가 파악해야 하는 사항
  
| 항목 | 설명 |
|:-----|:-----|
|[![엔터프라이즈 설계자 모델 축소판 그림을 위한 Microsoft 클라우드 보안.](../media/solutions-architecture-center/msft-cloud-security-model-thumb.png)](https://download.microsoft.com/download/6/D/F/6DFD7614-BBCF-4572-A871-E446B8CF5D79/MSFT_cloud_architecture_security%20(1).pdf) <br/> [PDF](https://download.microsoft.com/download/6/D/F/6DFD7614-BBCF-4572-A871-E446B8CF5D79/MSFT_cloud_architecture_security%20(1).pdf)  \| <br/>2021년 4월에 업데이트되었습니다. | 이 모델에는 다음이 포함됩니다. <ul><li>Microsoft 및 고객 보안 책임</li><li>ID 및 장치 액세스</li><li>위협 방지</li><li>정보 보호 </ul><br/>|
   
<a name="networking"></a>
### <a name="microsoft-cloud-networking-for-it-architects"></a>IT 설계자용 Microsoft 클라우드 네트워킹

Microsoft 클라우드 서비스 및 플랫폼의 네트워킹과 관련하여 IT 설계자가 파악해야 하는 사항
  
| 항목 | 설명 |
|:-----|:-----|
|[![Microsoft 클라우드 네트워킹 모델의 축소판 이미지입니다.](../media/solutions-architecture-center/msft-cloud-networking-model-thumb.png)](../downloads/MSFT_cloud_architecture_networking.pdf) <br/>  [PDF로 보기](../downloads/MSFT_cloud_architecture_networking.pdf) \| [PDF로 다운로드](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_networking.pdf) \| [앱으로 Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_networking.vsdx)   <br/>2020년 8월에 업데이트되었습니다. | 이 모델에는 다음이 포함됩니다. <ul><li> 클라우드 연결을 위해 네트워크 확장 </li><li> Microsoft 클라우드 연결의 공통 요소 </li><li> Microsoft 클라우드 연결을 위한 ExpressRoute </li><li> Microsoft SaaS, Azure PaaS 및 Azure IaaS에 대한 네트워킹 디자인 </li></ul><br/>  <br/>|

<a name="hybrid"></a>
### <a name="microsoft-hybrid-cloud-for-it-architects"></a>IT 설계자용 Microsoft 하이브리드 클라우드

Microsoft 서비스 및 플랫폼용 하이브리드 클라우드와 관련하여 IT 설계자가 파악해야 하는 사항
  
| 항목 | 설명 |
|:-----|:-----|
|[![Microsoft 하이브리드 클라우드 모델의 축소판 이미지입니다.](../media/solutions-architecture-center/msft-hybrid-cloud-model-thumb.png)](../downloads/MSFT_cloud_architecture_hybrid.pdf) <br/> [PDF로 보기](../downloads/MSFT_cloud_architecture_hybrid.pdf) \| [PDF로 다운로드](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_hybrid.pdf) \| [앱으로 Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_hybrid.vsdx)     <br>2020년 8월에 업데이트되었습니다. | 이 모델에는 다음이 포함됩니다. <ul><li> Microsoft 클라우드 서비스(SaaS, Azure PaaS, Azure IaaS) 및 공통 요소 </li><li> Microsoft 클라우드 서비스를 위한 하이브리드 클라우드 아키텍처 </li><li> Microsoft SaaS(Office 365), Azure PaaS, Azure IaaS를 위한 하이브리드 클라우드 시나리오 </li></ul><br/>|

### <a name="architecture-approaches-for-microsoft-cloud-tenant-to-tenant-migrations"></a>Microsoft 클라우드 테넌트간 마이그레이션에 대한 아키텍처 접근 방식 
이 시리즈에서는 합병, 인수, 매각 및 기타 시나리오를 통해 새로운 클라우드 테넌트로 마이그레이션 할 수 있는 몇 가지 아키텍처 접근 방식에 대해 설명합니다. 이러한 항목에서는 Enterprise 자원 계획을 위한 시작점 지침을 제공합니다. 

| 항목 | 설명 |
|:-----|:-----|
|[![Microsoft 클라우드 테넌트-테넌트 마이그레이션을 위한 축소판 이미지입니다.](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) <br/> [PDF](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) \| 2021년 2월에 업데이트되었습니다.    |이 모델에는 다음이 포함됩니다. <ul><li>아키텍처 접근 방식에 대한 비즈니스 시나리오 매핑</li><li>디자인 고려 사항</li><li>단일 이벤트 마이그레이션 흐름 예</li><li>단계적 마이그레이션 흐름 예</li><li>테넌트 이동 또는 분할 흐름 예제</li></ul>|



