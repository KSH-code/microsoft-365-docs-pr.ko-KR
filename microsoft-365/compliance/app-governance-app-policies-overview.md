---
title: 정책에 관한 자세한 정보
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 정책에 관한 자세한 정보입니다.
ms.openlocfilehash: 6d4ff23ca0e09f5e410d32d6ced144afc0c4bb15
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420360"
---
# <a name="learn-about-app-policies"></a><span data-ttu-id="092e9-103">정책에 관한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="092e9-103">Learn about app policies</span></span>

><span data-ttu-id="092e9-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="092e9-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="092e9-105">Microsoft 앱 거버넌스는 Microsoft 365 테넌트에서 비정상적인 앱 동작을 탐지하여 사용자가 보고 조사하고 해결할 수 있는 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="092e9-105">Microsoft app governance detects anomalous app behavior in your Microsoft 365 tenant and generates alerts that you can see, investigate, and resolve.</span></span> <span data-ttu-id="092e9-106">이 기본 제공 탐지 기능 외에도 기본 서식 파일 집합을 사용하여 다른 경고를 생성하는 고유한 앱 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="092e9-106">Beyond this built-in detection capability, you can use a set of default templates to create your own app policies that generate other alerts.</span></span>

<span data-ttu-id="092e9-107">앱 및 사용자 패턴 및 행위에 대한 이러한 정책은 사용자가 비준수 또는 악성 앱을 사용하지 못하도록 보호하고 위험한 앱의 테넌트 데이터에 대한 액세스를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="092e9-107">These policies for app and user patterns and behaviors can protect your users from using non-compliant or malicious apps and limit the access of risky apps to your tenant data.</span></span>

<span data-ttu-id="092e9-108">다음은 앱 정책 관리에 필요한 관리자 역할에 대한 간단한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="092e9-108">Here's a quick review of required administrator roles for app policy management.</span></span>

| <span data-ttu-id="092e9-109">역할</span><span class="sxs-lookup"><span data-stu-id="092e9-109">Role</span></span> | <span data-ttu-id="092e9-110">정책 읽기</span><span class="sxs-lookup"><span data-stu-id="092e9-110">Read policies</span></span> | <span data-ttu-id="092e9-111">정책 만들기, 업데이트 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="092e9-111">Create, update, or delete policies</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="092e9-112">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="092e9-112">Compliance Administrator</span></span> | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |
| <span data-ttu-id="092e9-115">규정 준수 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="092e9-115">Compliance Reader</span></span> | ![확인 표시](..\media\checkmark.png) |  |
| <span data-ttu-id="092e9-117">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="092e9-117">Global Administrator</span></span> | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |
| <span data-ttu-id="092e9-120">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="092e9-120">Global Reader</span></span>  | ![확인 표시](..\media\checkmark.png) |  |
| <span data-ttu-id="092e9-122">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="092e9-122">Security Administrator</span></span> | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |
| <span data-ttu-id="092e9-125">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="092e9-125">Security Reader</span></span>  | ![확인 표시](..\media\checkmark.png) |  |
| <span data-ttu-id="092e9-127">보안 운영자</span><span class="sxs-lookup"><span data-stu-id="092e9-127">Security Operator</span></span> | ![확인 표시](..\media\checkmark.png) | ![확인 표시](..\media\checkmark.png) |
||||

<!--
How app policies are the method by which MAPG detects app anomolies resulting in detection (alerts) and remediation (manual or automatic) 


CFA #2 Scenario 1: As an admin, I can quickly set up policies to govern M365 apps in my tenant using MAPG out-of-the-box templates
CFA #2 Scenario 2: As an admin, I can create customized policies to govern M365 apps in my tenant to meet my organizations requirements.
CFA #2 Scenario 3: As an admin or policy reviewer, I can view all policies created in my environment and quickly see which policies have associated alerts. 
CFA #2 Scenario 4: As an admin, I can adjust policies efficiently to meet changing needs.

App policy templates

- Basic info
- Policy settings and conditions
- Actions
- Status

--> 

## <a name="next-step"></a><span data-ttu-id="092e9-130">다음 단계</span><span class="sxs-lookup"><span data-stu-id="092e9-130">Next step</span></span>

[<span data-ttu-id="092e9-131">앱 정책 시작하기.</span><span class="sxs-lookup"><span data-stu-id="092e9-131">Get started with app policies.</span></span>](app-governance-app-policies-get-started.md)
