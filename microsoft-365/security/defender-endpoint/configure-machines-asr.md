---
title: ASR 규칙 배포 및 검색 최적화
description: 일반적인 맬웨어 악용을 식별하고 방지하기 위해 ASR(공격 표면 축소) 규칙을 최적화합니다.
keywords: 온보드, Intune 관리, 끝점용 Microsoft Defender, Microsoft Defender, Windows Defender, 공격 표면 감소, ASR, 보안 기준
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 91295135c833c6b403078bdfd517c7b84ec7d630
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932850"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a><span data-ttu-id="753e5-104">ASR 규칙 배포 및 검색 최적화</span><span class="sxs-lookup"><span data-stu-id="753e5-104">Optimize ASR rule deployment and detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="753e5-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="753e5-105">**Applies to:**</span></span>
- [<span data-ttu-id="753e5-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="753e5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="753e5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="753e5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="753e5-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="753e5-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="753e5-109">[무료 평가판에 등록합니다.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="753e5-109">[Sign up for a free trial](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span></span>

<span data-ttu-id="753e5-110">[ASR(공격 표면 감소) 규칙은](./attack-surface-reduction.md) 일반적인 맬웨어 악용을 식별하고 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="753e5-110">[Attack surface reduction (ASR) rules](./attack-surface-reduction.md) identify and prevent typical malware exploits.</span></span> <span data-ttu-id="753e5-111">잠재적으로 악성 코드가 실행될 수 있는 경우와 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="753e5-111">They control when and how potentially malicious code can run.</span></span> <span data-ttu-id="753e5-112">예를 들어 JavaScript 또는 VBScript가 다운로드된 실행 파일을 시작하지 못하게 방지하고, Office 매크로에서 Win32 API 호출을 차단하고, USB 드라이브에서 실행되는 프로세스를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="753e5-112">For example, they can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, and block processes that run from USB drives.</span></span>

<span data-ttu-id="753e5-113">![공격 표면 관리 카드](images/secconmgmt_asr_card.png)</span><span class="sxs-lookup"><span data-stu-id="753e5-113">![Attack surface management card](images/secconmgmt_asr_card.png)</span></span><br>
<span data-ttu-id="753e5-114">*공격 표면 관리 카드*</span><span class="sxs-lookup"><span data-stu-id="753e5-114">*Attack surface management card*</span></span>

<span data-ttu-id="753e5-115">공격 *표면 관리 카드는* 다음에 사용할 수 있는 Microsoft 365 보안 센터의 도구 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="753e5-115">The *Attack surface management card* is an entry point to tools in Microsoft 365 security center that you can use to:</span></span>

* <span data-ttu-id="753e5-116">ASR 규칙이 현재 조직에 배포되는 방법을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="753e5-116">Understand how ASR rules are currently deployed in your organization.</span></span>
* <span data-ttu-id="753e5-117">ASR 검색을 검토하고 가능한 잘못된 검색을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="753e5-117">Review ASR detections and identify possible incorrect detections.</span></span>
* <span data-ttu-id="753e5-118">제외의 영향을 분석하고 제외할 파일 경로 목록을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="753e5-118">Analyze the impact of exclusions and generate the list of file paths to exclude.</span></span>

<span data-ttu-id="753e5-119">Go **to attack surface management**  >  **Monitoring & reports > Attack surface reduction rules > Add exclusions 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="753e5-119">Select **Go to attack surface management** > **Monitoring & reports > Attack surface reduction rules > Add exclusions**.</span></span> <span data-ttu-id="753e5-120">Microsoft 365 보안 센터의 다른 섹션으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="753e5-120">From there, you can navigate to other sections of Microsoft 365 security center.</span></span>

<span data-ttu-id="753e5-121">![Microsoft 365 보안 센터의 공격 표면 축소 규칙 페이지에서 제외 탭 추가](images/secconmgmt_asr_m365exlusions.png)</span><span class="sxs-lookup"><span data-stu-id="753e5-121">![Add exclusions tab in the Attack surface reduction rules page in Microsoft 365 security center](images/secconmgmt_asr_m365exlusions.png)</span></span><br>
<span data-ttu-id="753e5-122">*Microsoft 365 보안 센터의 공격 표면 축소 규칙 페이지의 제외 추가 탭*</span><span class="sxs-lookup"><span data-stu-id="753e5-122">The ***Add exclusions** tab in the Attack surface reduction rules page in Microsoft 365 security center*</span></span>

> [!NOTE]
> <span data-ttu-id="753e5-123">Microsoft 365 보안 센터에 액세스하려면 Microsoft 365 E3 또는 E5 라이선스와 Azure Active Directory에서 특정 역할이 있는 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="753e5-123">To access Microsoft 365 security center, you need a Microsoft 365 E3 or E5 license and an account that has certain roles on Azure Active Directory.</span></span> <span data-ttu-id="753e5-124">[필요한 라이선스 및 사용 권한에 대해 읽어 읽습니다.](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="753e5-124">[Read about required licenses and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="753e5-125">Microsoft 365 보안 센터의 ASR 규칙 배포에 대한 자세한 내용은 ASR 규칙 배포 및 검색 모니터링 및 관리를 [참조하세요.](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)</span><span class="sxs-lookup"><span data-stu-id="753e5-125">For more information about ASR rule deployment in Microsoft 365 security center, see [Monitor and manage ASR rule deployment and detections](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).</span></span>

<span data-ttu-id="753e5-126">**관련 항목**</span><span class="sxs-lookup"><span data-stu-id="753e5-126">**Related topics**</span></span>

* [<span data-ttu-id="753e5-127">장치가 올바르게 구성되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="753e5-127">Ensure your devices are configured properly</span></span>](configure-machines.md)
* [<span data-ttu-id="753e5-128">끝점용 Microsoft Defender에 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="753e5-128">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
* [<span data-ttu-id="753e5-129">끝점 보안 기준에 대한 Microsoft Defender 준수 모니터링</span><span class="sxs-lookup"><span data-stu-id="753e5-129">Monitor compliance to the Microsoft Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
