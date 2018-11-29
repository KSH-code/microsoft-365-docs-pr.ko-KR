---
title: Office 365 ProPlus 배포 종료 조건
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/29/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 구성이 Office 365 ProPlus 인프라에 대한 Microsoft 365 Enterprise 조건을 충족하는지 확인합니다.
ms.openlocfilehash: c38539d85e1c826667b7a8a177a15ab75350aa5f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869706"
---
# <a name="office-365-proplus-deployment-exit-criteria"></a><span data-ttu-id="2c8dc-103">Office 365 ProPlus 배포 종료 조건</span><span class="sxs-lookup"><span data-stu-id="2c8dc-103">Office 365 ProPlus deployment exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)

<span data-ttu-id="2c8dc-104">*이 단계는 E3 및 E5 버전의 Microsoft 365 Enterprise 및 Microsoft 365 Education에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="2c8dc-104">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="2c8dc-105">배포 프로세스의 다음 단계로 진행하기 전에 구성이 Office 365 ProPlus 인프라에 대한 다음 필수 조건을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2c8dc-105">Before you move on to the next phase in the deployment process, ensure that your configuration meets the following required criteria for Office 365 ProPlus infrastructure.</span></span>

- <span data-ttu-id="2c8dc-106">다음과 같은 인프라 및 환경 평가 완료</span><span class="sxs-lookup"><span data-stu-id="2c8dc-106">Assessment of infrastructure and environment is complete, including:</span></span>

    - <span data-ttu-id="2c8dc-107">클라이언트 장치 정보</span><span class="sxs-lookup"><span data-stu-id="2c8dc-107">Client device details</span></span>
    - <span data-ttu-id="2c8dc-108">배포 도구</span><span class="sxs-lookup"><span data-stu-id="2c8dc-108">Deployment tools</span></span>
    - <span data-ttu-id="2c8dc-109">Office 365 라이선스 및 계정</span><span class="sxs-lookup"><span data-stu-id="2c8dc-109">Office 365 licensing and accounts</span></span>
    - <span data-ttu-id="2c8dc-110">네트워크 기능</span><span class="sxs-lookup"><span data-stu-id="2c8dc-110">Network capability</span></span>
    - <span data-ttu-id="2c8dc-111">응용 프로그램 호환성</span><span class="sxs-lookup"><span data-stu-id="2c8dc-111">Application compatibility</span></span>

- <span data-ttu-id="2c8dc-112">다음과 같은 배포 계획 완료</span><span class="sxs-lookup"><span data-stu-id="2c8dc-112">Deployment plan is complete, including:</span></span>

    - <span data-ttu-id="2c8dc-113">Office 365 ProPlus 배포 방법</span><span class="sxs-lookup"><span data-stu-id="2c8dc-113">How to deploy Office 365 ProPlus</span></span>
    - <span data-ttu-id="2c8dc-114">Office 365 ProPlus의 업데이트를 관리하는 방법</span><span class="sxs-lookup"><span data-stu-id="2c8dc-114">How to manage updates to Office 365 ProPlus</span></span>
    - <span data-ttu-id="2c8dc-115">네트워크의 로컬 원본에서 배포 및 설치할지 또는 클라우드에서 배포 및 설치할지 여부</span><span class="sxs-lookup"><span data-stu-id="2c8dc-115">Whether to deploy and install from a local source on your network or from the cloud</span></span>
    - <span data-ttu-id="2c8dc-116">가져올 업데이트 채널과 해당 클라이언트 장치</span><span class="sxs-lookup"><span data-stu-id="2c8dc-116">Which client devices get which update channels</span></span>
    - <span data-ttu-id="2c8dc-117">정의된 설치 패키지</span><span class="sxs-lookup"><span data-stu-id="2c8dc-117">Installation packages defined</span></span>
    - <span data-ttu-id="2c8dc-118">배포 그룹에 할당된 모든 클라이언트 장치</span><span class="sxs-lookup"><span data-stu-id="2c8dc-118">All client devices assigned to deployment groups</span></span>
    - <span data-ttu-id="2c8dc-119">실행할 Office 응용 프로그램, 아키텍처 및 언어와 해당 클라이언트 장치</span><span class="sxs-lookup"><span data-stu-id="2c8dc-119">Which Office applications, architectures, and languages go to which client devices</span></span>

- <span data-ttu-id="2c8dc-120">다음과 같은 Office 365 ProPlus 배포 완료</span><span class="sxs-lookup"><span data-stu-id="2c8dc-120">Deployment of Office 365 ProPlus is complete, including:</span></span>

    - <span data-ttu-id="2c8dc-121">모든 클라이언트 장치에 Office 365 ProPlus가 설치됨</span><span class="sxs-lookup"><span data-stu-id="2c8dc-121">All client devices have Office 365 ProPlus installed</span></span>
    - <span data-ttu-id="2c8dc-122">모든 클라이언트 장치가 적절한 업데이트 채널에서 업데이트를 받고 있음</span><span class="sxs-lookup"><span data-stu-id="2c8dc-122">All client devices are in the appropriate update channel and are receiving updates</span></span>
    - <span data-ttu-id="2c8dc-123">모든 클라이언트 장치에 적절한 언어가 설치되거나 사용 가능함</span><span class="sxs-lookup"><span data-stu-id="2c8dc-123">All client devices have the appropriate languages installed or available</span></span>

## <a name="next-phase"></a><span data-ttu-id="2c8dc-124">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2c8dc-124">Next phase</span></span> 


|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)| <span data-ttu-id="2c8dc-125">Microsoft 365 Enterprise에 대한 종단 간 배포 프로세스의 다음 단계는 [모바일 장치 관리](mobility-infrastructure.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="2c8dc-125">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [mobile device management](mobility-infrastructure.md).</span></span> |
