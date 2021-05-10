---
title: 에 대한 정의 사용 중지 Microsoft Defender 바이러스 백신
description: 에 대한 정의 사용 중지를 Microsoft Defender 바이러스 백신.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender, 정의 사용 중지
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
ms.openlocfilehash: 66b2e882a0f6de21e27dabb3a4bfe2fe113bcb32
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296499"
---
# <a name="turn-on-definition-retirement"></a><span data-ttu-id="0a961-104">정의 사용 중지 켜기</span><span class="sxs-lookup"><span data-stu-id="0a961-104">Turn on definition retirement</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0a961-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0a961-105">**Applies to:**</span></span>

- [<span data-ttu-id="0a961-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0a961-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0a961-107">그룹 정책을 사용하여 정의 사용 중지를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-107">You can configure definition retirement using Group Policy.</span></span> <span data-ttu-id="0a961-108">정의 사용 중지는 컴퓨터에 특정 취약점으로부터 보호하는 데 필요한 보안 업데이트가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-108">Definition retirement checks to see if a computer has the required security updates necessary to protect it against a particular vulnerability.</span></span> <span data-ttu-id="0a961-109">시스템이 정의에 의해 검색된 악용에 취약하지 않은 경우 해당 정의는 "사용 중지"됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-109">If the system is not vulnerable to the exploit detected by a definition, then that definition is "retired".</span></span> <span data-ttu-id="0a961-110">특정 프로토콜에 대한 모든 보안 인텔리전스가 사용 중지된 경우 해당 프로토콜은 더 이상 구문 분석하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-110">If all security intelligence for a given protocol are retired then that protocol is no longer parsed.</span></span> <span data-ttu-id="0a961-111">이 기능을 사용하도록 설정하면 성능을 개선하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-111">Enabling this feature helps to improve performance.</span></span> <span data-ttu-id="0a961-112">모든 최신 보안 업데이트가 있는 최신 컴퓨터에서 네트워크 보호는 네트워크 성능에 영향을 끼치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-112">On a computer that is up-to-date with all the latest security updates, network protection will have no impact on network performance.</span></span>

## <a name="use-group-policy-to-configure-definition-retirement"></a><span data-ttu-id="0a961-113">그룹 정책을 사용하여 정의 사용 중지 구성</span><span class="sxs-lookup"><span data-stu-id="0a961-113">Use Group Policy to configure definition retirement</span></span>

1. <span data-ttu-id="0a961-114">그룹 정책 관리 끝점에서 그룹 정책 관리 [콘솔 을 니다.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="0a961-114">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="0a961-115">컴퓨터 구성 **관리** 템플릿 Windows 네트워크 Microsoft Defender 바이러스 백신  >    >    >    >  **시스템으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="0a961-115">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="0a961-116">정의 **사용 중지 켜기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a961-116">Select **Turn on definition retirement**.</span></span> <span data-ttu-id="0a961-117">기본적으로 이 정책은 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-117">By default, this policy is enabled.</span></span> <span data-ttu-id="0a961-118">구성되지 **않은 것으로 설정된 경우** 정의 사용 중지가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-118">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="0a961-119">정책을 편집하려면 정책 설정 **편집 링크를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-119">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="0a961-120">사용 **을** 선택한 다음 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a961-120">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="0a961-121">업데이트된 그룹 정책 개체를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-121">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="0a961-122">그룹 [정책 관리 콘솔을 참조합니다.](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="0a961-122">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="0a961-123">그룹 정책 개체를 사용하는지 여부</span><span class="sxs-lookup"><span data-stu-id="0a961-123">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="0a961-124">클라우드에서 번역하는 방법을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-124">See how they translate in the cloud.</span></span> <span data-ttu-id="0a961-125">미리 보기에서 그룹 정책 분석을 사용하여 Microsoft Endpoint Manager 그룹 정책 개체를 [분석합니다.](/mem/intune/configuration/group-policy-analytics)</span><span class="sxs-lookup"><span data-stu-id="0a961-125">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="0a961-126">관련 문서</span><span class="sxs-lookup"><span data-stu-id="0a961-126">Related articles</span></span>

- [<span data-ttu-id="0a961-127">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="0a961-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="0a961-128">클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="0a961-128">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="0a961-129">맬웨어 방지 정책을 만들고 배포하는 방법: 클라우드 보호 서비스</span><span class="sxs-lookup"><span data-stu-id="0a961-129">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)