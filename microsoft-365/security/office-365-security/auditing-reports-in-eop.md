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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 관리자는 EOP(Exchange Online Protection)에서 사용할 수 있는 관리자 감사 보고서에 대해 검색할 수 있습니다.
ms.openlocfilehash: ab2c1af7197094b456d8e1b4151dd42791d992a1
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825788"
---
# <a name="auditing-reports-in-standalone-eop"></a><span data-ttu-id="ddaf7-103">독립 실행형 EOP에서 보고서 감사</span><span class="sxs-lookup"><span data-stu-id="ddaf7-103">Auditing reports in standalone EOP</span></span>

<span data-ttu-id="ddaf7-104">Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 감사 보고서를 통해 조직의 규제, 규정 준수 및 법적 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddaf7-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, auditing reports can help you meet regulatory, compliance, and litigation requirements for your organization.</span></span> <span data-ttu-id="ddaf7-105">언제든지 감사 보고서를 가져와 EOP 구성에 적용된 변경 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddaf7-105">You can obtain auditing reports at any time to determine the changes that have been made to your EOP configuration.</span></span> <span data-ttu-id="ddaf7-106">이러한 보고서를 사용하면 구성 문제를 해결하거나 보안 또는 규정 준수 관련 문제의 원인을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddaf7-106">These reports can help you troubleshoot configuration issues or find the cause of security-related or compliance-related problems.</span></span>

<span data-ttu-id="ddaf7-107">독립 실행형 EOP에서 사용할 수 있는 감사 보고서에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddaf7-107">There are two auditing reports available in standalone EOP:</span></span>

- <span data-ttu-id="ddaf7-108">**관리자 역할 그룹 보고서:** 관리자 역할 그룹 보고서에서는 사용자가 관리자 역할 그룹의 구성원에 추가되는 시기를 확인하거나 제거하는 방법을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddaf7-108">**Administrator role group report**: The administrator role group report lets you view when a user is added to or removed from membership in an administrator role group.</span></span> <span data-ttu-id="ddaf7-109">이 보고서를 사용하여 조직의 사용자에게 할당된 관리 권한 변경 내용을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddaf7-109">You can use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span> <span data-ttu-id="ddaf7-110">자세한 내용은 [EOP에서 관리자 역할 그룹 보고서 실행을 참조하세요.](run-an-administrator-role-group-report-in-eop-eop.md)</span><span class="sxs-lookup"><span data-stu-id="ddaf7-110">For more information, see [Run an administrator role group report in standalone EOP](run-an-administrator-role-group-report-in-eop-eop.md).</span></span>

- <span data-ttu-id="ddaf7-111">**관리자 감사 로그:** 관리자 감사 로그는 관리자 또는 관리자 권한이 있는 사용자에 의한 모든 작업(독립 실행형 EOP PowerShell cmdlet 기반)을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="ddaf7-111">**Administrator audit log**: The administrator audit log records any action (based on standalone EOP PowerShell cmdlets) by an admin or a user with administrative privileges.</span></span> <span data-ttu-id="ddaf7-112">자세한 내용은 [Exchange Online에서 관리자 감사 로그 보기를 참조하세요.](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log)</span><span class="sxs-lookup"><span data-stu-id="ddaf7-112">For more information, see [View the Administrator Audit Log in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log).</span></span>
