---
title: Windows의 정보 보호 개요
ms.reviewer: ''
description: Windows에서 정보 보호가 작동하는 방식에 대해 알아보고 중요한 정보를 식별하고 보호합니다.
keywords: 정보, 보호, dlp, 데이터, 손실, 방지, 보호
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6d8f76786d4ee0bb96221d765bc1c3de0523c391
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073855"
---
# <a name="information-protection-in-windows-overview"></a><span data-ttu-id="50df0-104">Windows의 정보 보호 개요</span><span class="sxs-lookup"><span data-stu-id="50df0-104">Information protection in Windows overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="50df0-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="50df0-105">**Applies to:**</span></span>

- [<span data-ttu-id="50df0-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="50df0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="50df0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50df0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="50df0-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="50df0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="50df0-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="50df0-110">정보 보호는 Microsoft 365 Enterprise 제품군의 중요한 부분으로, 작업 공간에서 생산성을 유지하면서 중요한 데이터를 안전하게 보호하는 지능형 보호 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-110">Information protection is an integral part of Microsoft 365 Enterprise suite, providing intelligent protection to keep sensitive data secure while enabling productivity in the workplace.</span></span>


>[!TIP]
> <span data-ttu-id="50df0-111">[Microsoft Defender ATP가 Microsoft Information Protection과](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)통합되어 Windows 장치에서 중요한 데이터를 검색, 보호 및 모니터링하는 방법에 대한 블로그 게시물을 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-111">Read our blog post about how [Microsoft Defender ATP integrates with Microsoft Information Protection to discover, protect, and monitor sensitive data on Windows devices](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/).</span></span>

<span data-ttu-id="50df0-112">Endpoint용 Defender는 다음 방법을 적용하여 데이터를 검색, 분류 및 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-112">Defender for Endpoint applies the following methods to discover, classify, and protect data:</span></span>

- <span data-ttu-id="50df0-113">**데이터 검색** - 위험에 노출된 Windows 장치에서 중요한 데이터 식별</span><span class="sxs-lookup"><span data-stu-id="50df0-113">**Data discovery** - Identify sensitive data on Windows devices at risk</span></span>
- <span data-ttu-id="50df0-114">**데이터 분류** - Office 365 보안 및 준수 센터에서 관리되는 일반적인 MIP(Microsoft Information Protection) 정책을 & 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-114">**Data classification** - Automatically classify data based on common Microsoft Information Protection (MIP) policies managed in Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="50df0-115">자동 분류를 사용하면 최종 사용자가 중요한 데이터를 수동으로 분류하지 않은 경우에도 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-115">Auto-classification allows you to protect sensitive data even if the end user hasn’t manually classified it.</span></span>


## <a name="data-discovery-and-data-classification"></a><span data-ttu-id="50df0-116">데이터 검색 및 데이터 분류</span><span class="sxs-lookup"><span data-stu-id="50df0-116">Data discovery and data classification</span></span>

<span data-ttu-id="50df0-117">Endpoint용 Defender는 민감도 레이블이 있는 파일과 중요한 정보 유형이 포함된 파일을 자동으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-117">Defender for Endpoint automatically discovers files with sensitivity labels and files that contain sensitive information types.</span></span>

<span data-ttu-id="50df0-118">민감도 레이블은 중요한 콘텐츠를 분류하고 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-118">Sensitivity labels classify and help protect sensitive content.</span></span>

<span data-ttu-id="50df0-119">Office 365 DLP(데이터 손실 방지) 구현의 중요한 정보 유형은 다음 두 가지 범주로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-119">Sensitive information types in the Office 365 data loss prevention (DLP) implementation fall under two categories:</span></span>

- <span data-ttu-id="50df0-120">기본</span><span class="sxs-lookup"><span data-stu-id="50df0-120">Default</span></span>
- <span data-ttu-id="50df0-121">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="50df0-121">Custom</span></span>

<span data-ttu-id="50df0-122">기본 중요한 정보 유형에는 은행 계좌 번호, 주민 번호 또는 국가 번호와 같은 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-122">Default sensitive information types include information such as bank account numbers, social security numbers, or national IDs.</span></span> <span data-ttu-id="50df0-123">자세한 내용은 중요한 정보 [유형이 를 찾아보는 것을 참조하세요.](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for)</span><span class="sxs-lookup"><span data-stu-id="50df0-123">For more information, see [What the sensitive information type look for](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for).</span></span>

<span data-ttu-id="50df0-124">사용자 지정 유형은 정의하는 유형으로, 다른 유형의 중요한 정보(예: 직원의 신분증 또는 프로젝트 번호)를 보호하도록 디자인되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-124">Custom types are ones that you define and is designed to protect a different type of sensitive information (for example, employee IDs or project numbers).</span></span> <span data-ttu-id="50df0-125">자세한 내용은 사용자 지정 중요한 정보 [유형 만들기를 참조하세요.](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type)</span><span class="sxs-lookup"><span data-stu-id="50df0-125">For more information see, [Create a custom sensitive information type](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type).</span></span>

<span data-ttu-id="50df0-126">Windows 장치에서 파일을 만들거나 편집하면 Endpoint용 Defender는 콘텐츠를 검사하여 중요한 정보가 포함되어 있는지 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-126">When a file is created or edited on a  Windows device, Defender for Endpoint scans the content to evaluate if it contains sensitive information.</span></span>

<span data-ttu-id="50df0-127">레이블 또는 정보 유형이 있는 경우 끝점용 Defender에서 중요한 정보를 포함하는 파일을 검색할 때 장치에서 Azure Information Protection에 자동으로 전달될 수 있도록 Azure Information Protection 통합을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-127">Turn on the Azure Information Protection integration so that when a file that contains sensitive information is discovered by Defender for Endpoint though labels or information types, it is automatically forwarded to Azure Information Protection from the device.</span></span>

![Azure Information Protection이 있는 설정 페이지의 이미지](images/atp-settings-aip.png)

<span data-ttu-id="50df0-129">보고된 신호는 Azure Information Protection - 데이터 검색 대시보드에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-129">The reported signals can be viewed on the Azure Information Protection – Data discovery dashboard.</span></span>

## <a name="azure-information-protection---data-discovery-dashboard"></a><span data-ttu-id="50df0-130">Azure Information Protection - 데이터 검색 대시보드</span><span class="sxs-lookup"><span data-stu-id="50df0-130">Azure Information Protection - Data discovery dashboard</span></span>

<span data-ttu-id="50df0-131">이 대시보드에서는 Endpoint용 Defender 및 Azure Information Protection에서 검색한 데이터의 요약된 검색 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-131">This dashboard presents a summarized discovery information of data discovered by both Defender for Endpoint and Azure Information Protection.</span></span> <span data-ttu-id="50df0-132">끝점용 Defender의 데이터는 위치 유형 - 끝점으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-132">Data from Defender for Endpoint is marked with Location Type - Endpoint.</span></span>

![Azure Information Protection의 이미지 - 데이터 검색](images/azure-data-discovery.png)

<span data-ttu-id="50df0-134">오른쪽의 장치 위험 열에서 이 장치 위험은 Endpoint용 Defender에서 직접 파생됩니다. 이는 끝점에 대한 Defender에서 감지된 활성 보안 위협에 따라 파일이 검색된 보안 장치의 위험 수준을 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-134">Notice the Device Risk column on the right, this device risk is derived directly from Defender for Endpoint, indicating the risk level of the security device where the file was discovered, based on the active security threats detected by Defender for Endpoint.</span></span>

<span data-ttu-id="50df0-135">디바이스를 클릭하여 민감도 레이블 및 정보 유형으로 이 디바이스에서 관찰된 파일 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-135">Click on a device to view a list of files observed on this device, with their sensitivity labels and information types.</span></span>

>[!NOTE]
><span data-ttu-id="50df0-136">Azure Information Protection 대시보드 검색에서 검색된 파일을 반영하도록 약 15-20분을 허용하세요.</span><span class="sxs-lookup"><span data-stu-id="50df0-136">Please allow approximately 15-20 minutes for the Azure Information Protection Dashboard Discovery to reflect discovered files.</span></span>

## <a name="log-analytics"></a><span data-ttu-id="50df0-137">Log Analytics</span><span class="sxs-lookup"><span data-stu-id="50df0-137">Log Analytics</span></span>

<span data-ttu-id="50df0-138">끝점용 Defender를 기반으로 하는 데이터 검색은 [Azure Log Analytics에서도](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)사용할 수 있습니다. 여기서 원시 데이터에 대해 복잡한 쿼리를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-138">Data discovery based on Defender for Endpoint is also available in [Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview), where you can perform complex queries over the raw data.</span></span>

<span data-ttu-id="50df0-139">Azure Information Protection 분석에 대한 자세한 내용은 Azure Information Protection에 대한 [중앙 보고를 참조하세요.](https://docs.microsoft.com/azure/information-protection/reports-aip)</span><span class="sxs-lookup"><span data-stu-id="50df0-139">For more information on Azure Information Protection analytics, see [Central reporting for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/reports-aip).</span></span>

<span data-ttu-id="50df0-140">Azure Portal에서 Azure Log Analytics를 열고 쿼리 작성기(표준 또는 클래식)를 여십시오.</span><span class="sxs-lookup"><span data-stu-id="50df0-140">Open Azure Log Analytics in Azure portal and open a query builder (standard or classic).</span></span>

<span data-ttu-id="50df0-141">끝점 데이터에 대한 Defender를 보기 위해 다음을 포함하는 쿼리를 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="50df0-141">To view Defender for Endpoint data, perform a query that contains:</span></span>

```
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

<span data-ttu-id="50df0-142">**선행 준비 사항:**</span><span class="sxs-lookup"><span data-stu-id="50df0-142">**Prerequisites:**</span></span>

- <span data-ttu-id="50df0-143">고객은 Azure Information Protection 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50df0-143">Customers must have a subscription for Azure Information Protection.</span></span>
- <span data-ttu-id="50df0-144">Microsoft Defender 보안 센터에서 Azure Information Protection 통합을 사용하도록 설정:</span><span class="sxs-lookup"><span data-stu-id="50df0-144">Enable Azure Information Protection integration in Microsoft Defender Security Center:</span></span>
    - <span data-ttu-id="50df0-145">Microsoft Defender 보안 **센터의** 설정으로 이동하여 일반 아래의 **고급 설정을** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="50df0-145">Go to **Settings** in Microsoft Defender Security Center, click on **Advanced Settings** under **General**.</span></span>



