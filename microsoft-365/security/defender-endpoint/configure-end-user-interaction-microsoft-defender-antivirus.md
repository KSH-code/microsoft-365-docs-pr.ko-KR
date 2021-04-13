---
title: 사용자가 Microsoft Defender AV와 상호 작용하는 방법 구성
description: 최종 사용자가 Microsoft Defender AV와 상호 작용하는 방법, 사용자에게 어떤 알림이 표시될지, 설정을 오버라이드할 수 있는지를 구성합니다.
keywords: 끝점, 사용자, 조작, 알림, UI 잠금 모드, 헤드리스 모드, 인터페이스 숨기기
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b0a26360e5a84d055ea97034a2d0fbd2bc0d5c09
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691553"
---
# <a name="configure-end-user-interaction-with-microsoft-defender-antivirus"></a><span data-ttu-id="7381b-104">Microsoft Defender 바이러스 백신과 최종 사용자 상호 작용 구성</span><span class="sxs-lookup"><span data-stu-id="7381b-104">Configure end-user interaction with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7381b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7381b-105">**Applies to:**</span></span>

- <span data-ttu-id="7381b-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="7381b-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="7381b-107">네트워크의 끝점 사용자가 Microsoft Defender 바이러스 백신과 상호 작용하는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7381b-107">You can configure how users of the endpoints on your network can interact with Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="7381b-108">여기에는 Microsoft Defender 바이러스 백신 인터페이스가 표시될지 여부, 사용자에게 어떤 알림이 표시되고, 전역으로 배포된 그룹 정책 설정을 로컬로 에버러할 수 있는지 여부가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7381b-108">This includes whether they see the Microsoft Defender Antivirus interface, what notifications they see, and if they can locally override globally-deployed Group Policy settings.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7381b-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="7381b-109">In this section</span></span>

<span data-ttu-id="7381b-110">항목</span><span class="sxs-lookup"><span data-stu-id="7381b-110">Topic</span></span> | <span data-ttu-id="7381b-111">설명</span><span class="sxs-lookup"><span data-stu-id="7381b-111">Description</span></span> 
---|---
[<span data-ttu-id="7381b-112">끝점에 나타나는 알림 구성</span><span class="sxs-lookup"><span data-stu-id="7381b-112">Configure notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md) | <span data-ttu-id="7381b-113">추가 알림 구성 및 사용자 지정, 알림에 대한 사용자 지정 텍스트 및 수정을 위해 재부팅에 대한 알림</span><span class="sxs-lookup"><span data-stu-id="7381b-113">Configure and customize additional notifications, customized text for notifications, and notifications about reboots for remediation</span></span>
[<span data-ttu-id="7381b-114">사용자가 Microsoft Defender 바이러스 백신 사용자 인터페이스를 보거나 상호 작용하지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="7381b-114">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="7381b-115">사용자로부터 사용자 인터페이스 숨기기</span><span class="sxs-lookup"><span data-stu-id="7381b-115">Hide the user interface from users</span></span>
[<span data-ttu-id="7381b-116">사용자가 로컬에서 정책 설정을 수정하지 못하도록 차단</span><span class="sxs-lookup"><span data-stu-id="7381b-116">Prevent users from locally modifying policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) | <span data-ttu-id="7381b-117">사용자가 개별 끝점에서 정책 설정을 재지정하지 못하도록 방지(또는 허용)</span><span class="sxs-lookup"><span data-stu-id="7381b-117">Prevent (or allow) users from overriding policy settings on their individual endpoints</span></span>