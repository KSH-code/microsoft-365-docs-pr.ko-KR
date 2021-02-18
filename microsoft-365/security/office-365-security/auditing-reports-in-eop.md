---
title: 독립 실행형 EOP에서 보고서 감사
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 관리자는 EOP(Exchange Online Protection)에서 사용할 수 있는 관리자 감사 보고서에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9508cd843b6986768158b5f036903869ced5a1b1
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286708"
---
# <a name="auditing-reports-in-standalone-eop"></a><span data-ttu-id="3ddf4-103">독립 실행형 EOP에서 보고서 감사</span><span class="sxs-lookup"><span data-stu-id="3ddf4-103">Auditing reports in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3ddf4-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="3ddf4-104">**Applies to**</span></span>
-  [<span data-ttu-id="3ddf4-105">Exchange Online Protection 독립 실행형</span><span class="sxs-lookup"><span data-stu-id="3ddf4-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="3ddf4-106">Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 감사 보고서를 통해 조직의 규정, 규정 준수 및 소송 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ddf4-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, auditing reports can help you meet regulatory, compliance, and litigation requirements for your organization.</span></span> <span data-ttu-id="3ddf4-107">언제든지 감사 보고서를 가져와 EOP 구성에 적용된 변경 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ddf4-107">You can obtain auditing reports at any time to determine the changes that have been made to your EOP configuration.</span></span> <span data-ttu-id="3ddf4-108">이러한 보고서를 사용하면 구성 문제를 해결하거나 보안 또는 규정 준수 관련 문제의 원인을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ddf4-108">These reports can help you troubleshoot configuration issues or find the cause of security-related or compliance-related problems.</span></span>

<span data-ttu-id="3ddf4-109">독립 실행형 EOP에서는 두 가지 감사 보고서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ddf4-109">There are two auditing reports available in standalone EOP:</span></span>

- <span data-ttu-id="3ddf4-110">**관리자 역할 그룹 보고서:** 관리자 역할 그룹 보고서를 통해 사용자가 관리자 역할 그룹의 구성원 자격에 추가되거나 제거된 경우를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ddf4-110">**Administrator role group report**: The administrator role group report lets you view when a user is added to or removed from membership in an administrator role group.</span></span> <span data-ttu-id="3ddf4-111">이 보고서를 사용하여 조직의 사용자에게 할당된 관리 권한 변경 내용을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ddf4-111">You can use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span> <span data-ttu-id="3ddf4-112">자세한 내용은 독립 실행형 EOP에서 관리자 역할 [그룹 보고서 실행을 참조하세요.](run-an-administrator-role-group-report-in-eop-eop.md)</span><span class="sxs-lookup"><span data-stu-id="3ddf4-112">For more information, see [Run an administrator role group report in standalone EOP](run-an-administrator-role-group-report-in-eop-eop.md).</span></span>

- <span data-ttu-id="3ddf4-113">**관리자 감사 로그:** 관리자 감사 로그는 관리자 또는 관리 권한이 있는 사용자의 모든 작업(독립 실행형 EOP PowerShell cmdlet 기반)을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="3ddf4-113">**Administrator audit log**: The administrator audit log records any action (based on standalone EOP PowerShell cmdlets) by an admin or a user with administrative privileges.</span></span> <span data-ttu-id="3ddf4-114">자세한 내용은 [Exchange Online에서 관리자 감사 로그 보기를 참조하세요.](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log)</span><span class="sxs-lookup"><span data-stu-id="3ddf4-114">For more information, see [View the Administrator Audit Log in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log).</span></span>
