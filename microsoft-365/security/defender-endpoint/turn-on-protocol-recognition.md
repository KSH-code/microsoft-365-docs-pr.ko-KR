---
title: 인증에 대한 프로토콜 Microsoft Defender 바이러스 백신
description: 프로토콜 인식을 Microsoft Defender 바이러스 백신.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender, 프로토콜 인식
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
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296492"
---
# <a name="turn-on-protocol-recognition"></a><span data-ttu-id="90530-104">프로토콜 인식 켜기</span><span class="sxs-lookup"><span data-stu-id="90530-104">Turn on protocol recognition</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="90530-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="90530-105">**Applies to:**</span></span>

- [<span data-ttu-id="90530-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="90530-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="90530-107">이 정책 설정을 통해 알려진 취약성 악용으로부터 네트워크 보호에 대한 프로토콜 인식을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90530-107">This policy setting allows you to configure protocol recognition for network protection against exploits of known vulnerabilities.</span></span> <span data-ttu-id="90530-108">이 설정을 사용하도록 설정하거나 구성하지 않은 경우 프로토콜 인식이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="90530-108">If you enable or do not configure this setting, protocol recognition will be enabled.</span></span> <span data-ttu-id="90530-109">이 설정을 사용하지 않도록 설정하면 프로토콜 인식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="90530-109">If you disable this setting, protocol recognition will be disabled.</span></span>

## <a name="use-group-policy-to-configure-protocol-recognition"></a><span data-ttu-id="90530-110">그룹 정책을 사용하여 프로토콜 인식 구성</span><span class="sxs-lookup"><span data-stu-id="90530-110">Use Group Policy to configure protocol recognition</span></span>

1. <span data-ttu-id="90530-111">그룹 정책 관리 끝점에서 그룹 정책 관리 [콘솔 을 니다.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="90530-111">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="90530-112">컴퓨터 구성 **관리** 템플릿 Windows 네트워크 Microsoft Defender 바이러스 백신  >    >    >    >  **시스템으로 이동하십시오.**</span><span class="sxs-lookup"><span data-stu-id="90530-112">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="90530-113">프로토콜 **인식 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="90530-113">Select **protocol recognition**.</span></span> <span data-ttu-id="90530-114">기본적으로 이 정책은 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="90530-114">By default, this policy is enabled.</span></span> <span data-ttu-id="90530-115">구성되지 **않은 것으로 설정된 경우** 정의 사용 중지가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="90530-115">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="90530-116">정책을 편집하려면 정책 설정 **편집 링크를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="90530-116">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="90530-117">사용 **을** 선택한 다음 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="90530-117">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="90530-118">업데이트된 그룹 정책 개체를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="90530-118">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="90530-119">그룹 [정책 관리 콘솔을 참조합니다.](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="90530-119">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="90530-120">그룹 정책 개체를 사용하는지 여부</span><span class="sxs-lookup"><span data-stu-id="90530-120">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="90530-121">클라우드에서 번역하는 방법을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="90530-121">See how they translate in the cloud.</span></span> <span data-ttu-id="90530-122">미리 보기에서 그룹 정책 분석을 사용하여 Microsoft Endpoint Manager 그룹 정책 개체를 [분석합니다.](/mem/intune/configuration/group-policy-analytics)</span><span class="sxs-lookup"><span data-stu-id="90530-122">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="90530-123">관련 문서</span><span class="sxs-lookup"><span data-stu-id="90530-123">Related articles</span></span>

- [<span data-ttu-id="90530-124">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="90530-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="90530-125">클라우드 제공 보호 사용</span><span class="sxs-lookup"><span data-stu-id="90530-125">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="90530-126">맬웨어 방지 정책을 만들고 배포하는 방법: 클라우드 보호 서비스</span><span class="sxs-lookup"><span data-stu-id="90530-126">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)