---
title: GDPR에 대한 Intune 데이터 주체 요청
description: Microsoft 제품, 서비스 및 관리 도구를 사용하여 통제자 고객이 개인 데이터를 찾아 조치를 취함으로써 DSR 요청에 대처하는 데 도움을 주는 방법에 대한 지침입니다.
keywords: Microsoft 365, Microsoft 365 Education, Microsoft 365 설명서, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: dougeby
author: dougeby
manager: angrobe
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 868bdf151f853168e7de69669b67e5686089ce72
ms.sourcegitcommit: 0dde96d5864e5b16ea24cfb302930b041c7a8091
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "34431449"
---
# <a name="intune-data-subject-requests-for-the-gdpr"></a>GDPR에 대한 Intune 데이터 주체 요청

EU GDPR(일반 데이터 보호 규정)은 사용자(규정에 *데이터 주체*로 알려짐)에게 고용주 또는 다른 유형의 대리점 및 조직(*데이터 통제자* 또는 단순히 *통제자*로 지칭)이 수집한 개인 데이터를 관리할 수 있는 권한을 부여합니다. 개인 데이터는 GDPR에서는 보다 광범위하게 식별되었거나 식별 가능한 자연인과 관련된 모든 데이터로 정의됩니다. GDPR은 데이터 주체에게 개인 데이터에 대한 특정 권한을 부여합니다. 이러한 권한에는 개인 데이터 복사본 획득, 수정 요청, 처리 제한, 삭제 또는 다른 통제자에게 이동될 수 있도록 전자 형식으로 수신하는 권한이 포함됩니다. 데이터 주체가 통제자에게 개인 데이터에 대해 조치를 취할 것을 요구하는 공식적인 요청을 *데이터 주체 요청* 또는 DSR이라고 합니다.

이 가이드에서는 Microsoft 제품, 서비스 및 관리 도구를 사용하여 통제자 고객이 DSR에 응답하기 위해 개인 데이터를 찾고 조치를 취하는 데 도움을 주는 방식을 설명합니다. 특히, Microsoft 클라우드에 있는 개인 데이터를 찾고, 액세스하고, 조치를 취하는 방법도 포함되어 있습니다. 이 가이드에 설명된 프로세스에 대한 간략한 개요는 다음과 같습니다.

1.  ***검색***—검색 도구를 사용하여 DSR의 대상이 될 수 있는 고객 데이터를 좀 더 쉽게 찾을 수 있습니다. 잠재적인 반응형 문서가 일단 수집되면 다음 단계에 설명된 DSR 작업 중 하나 이상을 수행하여 요청에 응답할 수 있습니다. 또는 요청이 DSR에 응답하기 위한 조직 지침을 충족하지 않는지도 확인할 수 있습니다.

2.  ***액세스***—Microsoft 클라우드에 있는 개인 데이터를 검색하고, 요청될 경우 데이터 주체가 사용할 수 있는 복사본을 만듭니다.

3.  ***수정***—해당되는 경우 개인 데이터를 변경하거나 요청된 다른 작업을 구현합니다.

4.  ***제한***—가능한 경우 다양한 Azure 서비스에 대한 라이선스를 제거하거나 원하는 서비스를 해제하여 개인 데이터의 처리를 제한합니다. 또한 Microsoft 클라우드에서 데이터를 제거하고 온-프레미스 또는 다른 위치에 유지할 수도 있습니다.

5.  ***삭제***Microsoft 클라우드에 있는 개인 데이터를 영구적으로 제거합니다.

6.  ***내보내기***—개인 데이터의 전자 사본(컴퓨터가 읽을 수 있는 형식)을 데이터 주체에게 제공합니다.

이 가이드의 각 섹션에서는 데이터 통제자가 Microsoft 클라우드의 개인 데이터에 대한 DSR에 응답하기 위해 수행할 수 있는 기술적 절차를 간략하게 설명합니다.

<span id="_Toc511384801" class="anchor"><span id="_Toc511163872" class="anchor"><span id="_Toc511136229" class="anchor"><span id="_Toc511125162" class="anchor"><span id="_Toc511120749" class="anchor"><span id="_Toc511122656" class="anchor"><span id="_Toc508792503" class="anchor"></span></span></span></span></span></span></span>
#### <a name="terminology"></a>용어

다음은 이 가이드와 관련된 용어의 정의입니다.

-   *통제자*—단독으로 또는 다른 대상과 함께 개인 데이터 처리의 목적 및 방법을 결정하는 자연인이나 법인, 공공 기관, 대리점 또는 기타 단체입니다. 이러한 처리의 목적 및 방법을 연합국 법률 또는 회원국 법률에 따라 결정하는 경우, 통제자 또는 구체적인 지명 기준을 연합국 법률 또는 회원국 법률에서 제공할 수 있습니다.

-   *개인 데이터* 및 *데이터 주체*—식별되었거나 식별 가능한 자연인(‘데이터 주체’)과 관련된 모든 정보입니다. 식별 가능한 자연인은 직간접적으로, 특히 이름, 식별 번호, 위치 데이터, 온라인 식별자 또는 해당 자연인의 신체적, 생리적, 유전적, 정신적, 경제적, 문화적 또는 사회적 ID와 같은 식별자를 참조하여 식별될 수 있는 사람입니다.

-   *프로세서*—통제자를 대신하여 개인 데이터를 처리하는 자연인이나 법인, 공공 기관, 대리점 또는 기타 단체입니다.

-   *고객 데이터*—엔터프라이즈 서비스를 사용하여 고객이 또는 고객을 대신해서 Microsoft에 제공되는 모든 텍스트, 사운드, 비디오 또는 이미지 파일, 소프트웨어를 포함하는 모든 데이터입니다. 고객 데이터에는 (1) 최종 사용자의 식별 가능 정보(예: 사용자 이름 및 Azure Active Directory의 연락처 정보) 및 고객이 특정 서비스에서 업로드하거나 만든 고객 콘텐츠(예: Azure Storage의 고객 콘텐츠, Azure SQL Database의 고객 콘텐츠 또는 Azure Virtual Machines의 고객 가상 머신 이미지)가 둘 다 포함됩니다.

-   *시스템 생성 로그*—Microsoft가 사용자에게 엔터프라이즈 서비스를 제공하는 데 도움을 주는 Microsoft 생성 로그 및 관련 데이터입니다. 시스템 생성 로그에는 일반적으로 자체적으로는 개인을 식별할 수 없지만 사용자에게 엔터프라이즈 서비스를 전달하는 데 사용되는 시스템 생성 번호에 해당하는 주로 필명화된 데이터(예: 고유 식별자)가 포함됩니다. 최종 사용자에 대한 식별 가능 정보(예: 사용자 이름)도 시스템 생성 로그에 포함될 수 있습니다.  

<span id="_Toc511384802" class="anchor"><span id="_Toc511163873" class="anchor"><span id="_Toc511136230" class="anchor"><span id="_Toc511125163" class="anchor"><span id="_Toc511120750" class="anchor"><span id="_Toc511122657" class="anchor"><span id="_Toc508792504" class="anchor"></span></span></span></span></span></span></span>

#### <a name="how-to-use-this-guide"></a>이 가이드를 사용하는 방법

이 가이드의 다음 두 부분으로 구성됩니다.

**1부: 고객 데이터에 대한 데이터 주체 요청에 응답** — 이 가이드 1부에서는 데이터를 작성한 애플리케이션에서 데이터를 액세스, 수정, 제한, 삭제 및 내보내는 방법을 설명합니다. 이 섹션에서는 최종 사용자의 고객 콘텐츠 및 식별 가능 정보에 대해 DSR을 실행하는 방법을 자세히 설명합니다.

**2부: 시스템 생성 로그에 대한 데이터 주 체 요청에 응답** — Microsoft의 엔터프라이즈 서비스를 사용할 경우, Microsoft는 서비스를 제공하기 위해 시스템 생성 로그라고 하는 정보를 생성합니다. 이 가이드의 2부에서는 Azure에서 이러한 정보를 액세스, 삭제 및 내보내는 방법을 설명합니다.

<span id="_Toc511384803" class="anchor"><span id="_Toc511163874" class="anchor"></span></span>







### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-intune"></a>Azure Active Directory 및 Microsoft Intune에 대한 DSR 이해

엔터프라이즈 고객에게 제공되는 서비스를 고려할 때, DSR의 실행은 항상 특정 AAD(Azure Active Directory) 테넌트의 컨텍스트 내에서 이해할 수 있어야 합니다. 특히 DSR은 항상 지정된 AAD 테넌트 내에서 실행됩니다. 사용자가 여러 테넌트에 참여하는 경우, 지정된 DSR이 *반드시* 요청이 수신된 특정 테넌트의 컨텍스트 내에서 실행된다는 점을 강조해서 알려주는 것이 중요합니다. 이러한 정보는 한 엔터프라이즈 고객의 DSR 실행이 인접 엔터프라이즈 고객의 데이터에 영향을 미치지 **않는다는 것**을 의미하므로 반드시 이해해야 합니다.

엔터프라이즈 고객에게 제공되는 Microsoft Intune도 마찬가지입니다. *AAD 테넌트와 연결된* Intune 계정에 대해 DSR을 실행할 경우 해당 테넌트 내의 데이터 **와만 관련됩니다**. 또한 테넌트 내에서 Intune 계정을 처리하는 경우에는 다음 사실을 이해해야 합니다.

-   Intune 사용자가 Azure 구독을 만들면 구독은 마치 AAD 테넌트인 것처럼 처리됩니다. 결과적으로 DSR은 위에 설명된 것처럼 테넌트 내로 한정됩니다.

-   Intune 계정을 통해 만든 Azure 구독을 삭제한 경우 실제 Intune 계정에는 **영향을 주지 않습니다**. 다시 말해서 위에서 언급한 것처럼 Azure 구독 내에서 실행되는 DSR은 테넌트 범위로 제한됩니다.

**지정된 테넌트의 외부에 있는** Intune 계정 자체에 대한 DSR은 소비자 개인 정보 보호 대시보드를 통해 실행됩니다. 자세한 내용은 Windows 데이터 주체 요청 가이드를 참조하세요.

<span id="_Toc508792505" class="anchor"><span id="_Toc511384804" class="anchor"><span id="_Toc511163875" class="anchor"><span id="_Toc511136231" class="anchor"><span id="_Toc511125164" class="anchor"><span id="_Toc511120751" class="anchor"><span id="_Toc511122658" class="anchor"></span></span></span></span></span></span></span>

## <a name="part-1-dsr-guide-for-customer-data"></a>1부: 고객 데이터에 대한 DSR 가이드

<span id="_Toc511384805" class="anchor"><span id="_Toc511163876" class="anchor"><span id="_Toc511136232" class="anchor"><span id="_Toc511125165" class="anchor"><span id="_Toc511120752" class="anchor"><span id="_Toc511122659" class="anchor"></span></span></span></span></span></span>

### <a name="executing-dsrs-against-customer-data"></a>고객 데이터에 대해 DSR 실행

Microsoft는 Azure Portal을 통해 또는 특정 서비스에 대한 기존 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 통해 직접(*제품 내 환경*) 특정 고객 데이터를 액세스, 삭제 및 내보내는 기능을 제공합니다. 제품 내 환경에 대한 자세한 내용은 해당 서비스 참조 설명서에 나와 있습니다.

>[!Important]  
>제품 내 DSR을 지원하는 서비스에서는 서비스의 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 직접적으로 사용하고 해당 CRUD(만들기, 읽기, 업데이트, 삭제) 작업을 설명해야 합니다. 따라서 지정된 데이터 주체에 대한 모든 요청을 완료하기 위해서는 Azure Portal 내의 DSR 외에도 지정된 서비스 내의 DSR도 실행해야 합니다. 자세한 내용은 특정 서비스 참조 설명서를 참조하세요.

<span id="_Discover" class="anchor"><span id="_Toc508792508" class="anchor"><span id="_Toc511122661" class="anchor"><span id="_Toc511120754" class="anchor"><span id="_Toc511125167" class="anchor"><span id="_Toc511136234" class="anchor"><span id="_Toc511163877" class="anchor"><span id="_Toc511384806" class="anchor"></span></span></span></span></span></span></span></span>
### <a name="step-1-discover"></a>1단계: 검색

DSR에 응답하는 첫 번째 단계는 요청의 대상인 개인 데이터를 찾는 것입니다. 첫 번째 단계인 문제의 개인 데이터 찾기 및 검토 작업은 DSR이 DSR 적용 또는 거부에 대한 조직 요건을 충족하는지 여부를 결정하는 데 도움이 됩니다. 예를 들어, 문제의 개인 데이터를 찾아서 검토한 후에는 요청이 조직 요건을 충족하지 않는지 판단할 수 있습니다. 조직 요건을 충족하지 못하면 타인의 권리와 자유에 부정적인 영향을 미칠 수 있기 때문입니다.

데이터를 찾은 후에 데이터 주체의 요청을 충족하기 위한 특정 작업을 수행할 수 있습니다. 자세한 내용은 다음을 참조하세요.
- [데이터 수집](https://docs.microsoft.com/intune/privacy-data-collect)
- [데이터 저장 및 처리](https://docs.microsoft.com/intune/privacy-data-store-process)
- [개인 데이터 보기](https://docs.microsoft.com/intune/privacy-data-view-correct#view-personal-data)

### <a name="step-2-access"></a>2단계: 액세스
DSR에 응답하는 개인 데이터가 포함된 고객 데이터를 찾은 후에 귀하와 조직은 데이터 주체에게 제공할 데이터를 결정해야 합니다. 실제 문서의 사본, 적절히 수정된 버전 또는 공유할 수 있는 부분의 스크린샷을 제공할 수 있습니다. 액세스 요청에 대한 이러한 각 응답에 대해, 응답 데이터를 포함하는 문서 또는 기타 항목 사본을 검색해야 합니다.

데이터 주체에 사본을 제공할 때는 다른 데이터 주체에 대한 개인 정보와 모든 기밀 정보를 제거하거나 수정해야 할 수 있습니다.

<span id="_Using_Content_Search_1" class="anchor"></span>다음은 DSR 액세스 요청에 대한 응답으로 데이터 복사본을 다운로드하는 방법을 설명합니다.

<span id="_Rectify" class="anchor"><span id="_Ref511119463" class="anchor"><span id="_Toc511122665" class="anchor"><span id="_Toc511120758" class="anchor"><span id="_Toc511125171" class="anchor"><span id="_Toc511136238" class="anchor"><span id="_Toc511163881" class="anchor"><span id="_Toc511384810" class="anchor"></span></span></span></span></span></span></span></span>

#### <a name="azure-active-directory"></a>Azure Active Directory

<span id="_Forms_1" class="anchor"></span>Microsoft에서는 엔터프라이즈 고객의 테넌트 관리자에게 DSR 액세스 요청을 관리할 수 있는 기능을 제공하는 포털 및 제품 환경을 둘 다 제공합니다. DSR 액세스 요청은 (a) 최종 사용자에 대한 식별 정보와 (b) 시스템 생성 로그를 포함하여 사용자의 개인 데이터에 액세스할 수 있도록 합니다.

<span id="_Toc511384811" class="anchor"><span id="_Toc511163882" class="anchor"><span id="_Toc511136239" class="anchor"><span id="_Toc511125172" class="anchor"><span id="_Toc511120759" class="anchor"><span id="_Toc511122666" class="anchor"></span></span></span></span></span></span>
#### <a name="service-specific-interfaces"></a>서비스 관련 인터페이스

Microsoft Intune은 사용자 인터페이스(UI) 또는 기존 응용 프로그래밍 인터페이스(API)를 통해 직접 [고객 데이터를 검색](#step-1-discover)할 수 있는 능력을 제공합니다.

<span id="_Sway" class="anchor"><span id="_Toc508792516" class="anchor"><span id="_Toc511122667" class="anchor"><span id="_Toc511120760" class="anchor"><span id="_Toc511125173" class="anchor"><span id="_Toc511136240" class="anchor"><span id="_Toc511163883" class="anchor"><span id="_Toc511384812" class="anchor"></span></span></span></span></span></span></span></span>
### <a name="step-3-rectify"></a>3단계: 수정

데이터 주체가 조직 데이터에 포함된 개인 데이터를 수정할 것을 요청한 경우 귀하와 조직은 요청을 수락하는 것이 적절한지 여부를 결정해야 합니다. 데이터 수정에는 개인 데이터의 편집, 수정 또는 문서나 기타 형식 또는 항목에서 개인 데이터를 제거하는 것과 같은 작업이 포함될 수 있습니다. 

<span id="_Toc511384813" class="anchor"><span id="_Toc511163884" class="anchor"><span id="_Toc511136241" class="anchor"><span id="_Toc511125174" class="anchor"><span id="_Toc511120761" class="anchor"><span id="_Toc511122668" class="anchor"></span></span></span></span></span></span>


 데이터 프로세서로, Microsoft는 실제 활동을 반영하고 Microsoft 서비스 내의 이벤트 기록 레코드를 구성하므로 시스템 생성 로그를 수정할 수 있는 기능을 제공하지 않습니다. Intune과 관려하여 관리자는 장치 또는 앱 특정 정보를 업데이트할 수 없습니다. 최종 사용자가 개인 데이터(장치 이름 등)를 수정하고자 한다면 장치에서 직접 수행해야 합니다. 이러한 변경 사항은 다음번에 Intune에 연결할 때 동기화됩니다.

### <a name="step-4-restrict"></a>4단계: 제한

<span id="_Delete" class="anchor"></span>데이터 주체는 개인 데이터 처리를 제한할 것을 요청할 수 있습니다. Microsoft는 Azure Portal과 기존의 API(응용 프로그래밍 인터페이스) 또는 UI(사용자 인터페이스)를 둘 다 제공합니다. 이러한 환경은 엔터프라이즈 고객의 테넌트 관리자가 데이터 내보내기 및 데이터 삭제를 조합하여 이러한 DSR을 관리할 수 있도록 합니다. 자세한 내용은 [개인 데이터 처리](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data)를 참조하세요.

<span id="_Toc508792528" class="anchor"><span id="_Toc511122671" class="anchor"><span id="_Toc511120764" class="anchor"><span id="_Toc511125177" class="anchor"><span id="_Toc511136244" class="anchor"><span id="_Toc511163887" class="anchor"><span id="_Toc511384816" class="anchor"></span></span></span></span></span></span></span>
### <a name="step-5-delete"></a>5단계: 삭제

조직의 고객 데이터에서 개인 데이터를 제거할 수 있는 “삭제할 권리”는 GDPR의 주요 보호 수단입니다. 감사 로그 정보를 제외한 모든 개인 데이터 및 시스템 생성 로그 제거를 포함하여 개인 데이터를 제거합니다. 자세한 내용은 [최종 사용자 개인 데이터 삭제](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data)를 참조하세요.


<span id="_Toc511384822" class="anchor"><span id="_Toc511163893" class="anchor"><span id="_Toc511136250" class="anchor"><span id="_Toc511125183" class="anchor"><span id="_Toc511120770" class="anchor"><span id="_Toc511122677" class="anchor"></span></span></span></span></span></span>
## <a name="part-2-system-generated-logs"></a>2부: 시스템 생성 로그
감사 로그는 테넌트 관리자에게 Microsoft Intune에서 변경 사항을 생성하는 활동 기록을 제공합니다. 감사 로그는 많은 활동을 관리하고 일반적으로 작업을 만들고, 업데이트(편집)하고 삭제하고 할당할 수 있습니다. 감사 이벤트를 만드는 원격 태스크도 검토할 수 있습니다. 이러한 감사 로그에는 장치가 UIntune에 등록된 사용자의 개인 데이터가 포함될 수 있습니다. 자세한 내용은 [개인 데이터 감사](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data)를 참조하세요.


## <a name="notify-about-exporting-or-deleting-issues"></a>내보내기 또는 삭제 문제에 대한 알림
Azure Portal에서 데이터를 내보내거나 삭제하는 동안 문제가 발생하면 Azure Portal **도움말 + 지원** 블레이드로 이동하여 **등록 관리 > 기타 보안 및 준수 요청 > 개인 정보 보호 블레이드 및 GDPR 요청**에서 새 티켓을 제출합니다.

#### <a name="learn-more"></a>자세한 정보
[Microsoft 보안 센터](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)