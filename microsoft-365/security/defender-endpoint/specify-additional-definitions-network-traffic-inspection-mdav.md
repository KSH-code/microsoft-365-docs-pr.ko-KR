---
title: 네트워크 트래픽 검사에 대한 추가 정의 집합을 Microsoft Defender 바이러스 백신
description: 네트워크 트래픽 검사에 대한 추가 정의 집합을 Microsoft Defender 바이러스 백신.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender, 네트워크 트래픽 검사
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300258"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="b84ae-104">네트워크 트래픽 검사에 대한 추가 정의 집합 지정</span><span class="sxs-lookup"><span data-stu-id="b84ae-104">Specify additional definition sets for network traffic inspection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b84ae-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b84ae-105">**Applies to:**</span></span>

- [<span data-ttu-id="b84ae-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b84ae-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b84ae-107">그룹 정책을 사용하여 네트워크 트래픽 검사에 대한 추가 정의 집합을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b84ae-107">You can specify additional definition sets for network traffic inspection using Group Policy.</span></span>

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="b84ae-108">그룹 정책을 사용하여 네트워크 트래픽 검사에 대한 추가 정의 집합 지정</span><span class="sxs-lookup"><span data-stu-id="b84ae-108">Use Group Policy to specify additional definition sets for network traffic inspection</span></span>

1. <span data-ttu-id="b84ae-109">그룹 정책 관리 끝점에서 그룹 정책 관리 [콘솔 을 니다.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="b84ae-109">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="b84ae-110">네트워크 **검사 Windows 구성**  >  **Microsoft Defender 바이러스 백신**  >  **로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="b84ae-110">Go to **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="b84ae-111">네트워크 트래픽 검사에 대한 추가 정의 **집합 지정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b84ae-111">Select **Specify additional definition sets for network traffic inspection**.</span></span> <span data-ttu-id="b84ae-112">기본적으로 이 정책은 **구성되지 않습니다.로 설정됩니다.**</span><span class="sxs-lookup"><span data-stu-id="b84ae-112">By default, this policy is set to **Not configured**.</span></span> 

4. <span data-ttu-id="b84ae-113">정책을 편집하려면 정책 설정 **편집 링크를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b84ae-113">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="b84ae-114">사용 **을** 선택한 다음 옵션 **섹션에서** **표시...를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b84ae-114">Select **Enabled**, and then in the **Options** section, select **Show...**.</span></span>

6. <span data-ttu-id="b84ae-115">목록에 항목을 추가한 다음 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b84ae-115">Add entries to the list, and then select **OK**.</span></span> 

   <span data-ttu-id="b84ae-116">각 항목은 이름-값 쌍으로 나열되어야 합니다. 여기서 이름은 정의 집합 GUID의 문자열 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="b84ae-116">Each entry must be listed as a name-value pair, where the name is a string representation of a definition set GUID.</span></span> <span data-ttu-id="b84ae-117">예를 들어 테스트 보안 인텔리전스를 사용하도록 설정하는 정의 집합 GUID는 으로 `{b54b6ac9-a737-498e-9120-6616ad3bf590}` 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="b84ae-117">As an example, the definition set GUID to enable test security intelligence is defined as: `{b54b6ac9-a737-498e-9120-6616ad3bf590}`.</span></span> <span data-ttu-id="b84ae-118">값은 사용되지 않습니다. 따라서 으로 설정하는 것이 `0` 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b84ae-118">The value is not used, so we recommend setting it to `0`.</span></span> 

7. <span data-ttu-id="b84ae-119">**확인을** 선택한 다음 업데이트된 그룹 정책 개체를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="b84ae-119">Select **OK**, and then deploy your updated Group Policy Object.</span></span> <span data-ttu-id="b84ae-120">그룹 [정책 관리 콘솔을 참조합니다.](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="b84ae-120">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="b84ae-121">그룹 정책 개체를 사용하는지 여부</span><span class="sxs-lookup"><span data-stu-id="b84ae-121">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="b84ae-122">클라우드에서 번역하는 방법을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b84ae-122">See how they translate in the cloud.</span></span> <span data-ttu-id="b84ae-123">미리 보기에서 그룹 정책 분석을 사용하여 Microsoft Endpoint Manager 그룹 정책 개체를 [분석합니다.](/mem/intune/configuration/group-policy-analytics)</span><span class="sxs-lookup"><span data-stu-id="b84ae-123">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="b84ae-124">관련 문서</span><span class="sxs-lookup"><span data-stu-id="b84ae-124">Related articles</span></span>

- [<span data-ttu-id="b84ae-125">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="b84ae-125">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="b84ae-126">클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="b84ae-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="b84ae-127">맬웨어 방지 정책을 만들고 배포하는 방법: 클라우드 보호 서비스</span><span class="sxs-lookup"><span data-stu-id="b84ae-127">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)