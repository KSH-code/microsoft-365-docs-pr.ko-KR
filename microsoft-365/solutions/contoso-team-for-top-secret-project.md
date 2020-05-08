---
title: Contoso Corporation의 최상위 비밀 프로젝트에 대 한 격리 된 팀
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- M365solutions
ms.custom: Ent_Architecture
description: '요약: Contoso에서 최상위 비밀 프로젝트에 대해 보안 격리를 적용 하 여 팀을 사용 하 여 새로운 제품 및 서비스 제품군을 개발 하는 방법을 설명 합니다.'
ms.openlocfilehash: 1083c9d3db3be9ca528b2eee40f072aa17c7431e
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159458"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="1c3ab-103">Contoso Corporation의 최상위 비밀 프로젝트에 대 한 격리 된 팀</span><span class="sxs-lookup"><span data-stu-id="1c3ab-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="1c3ab-104">경영진은이 Contoso의 CEO가 향후 5 년 동안 Contoso의 이익을 두 배로 만들 수 있는 새로운 제품 및 서비스 제품군의 개발을 주문 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="1c3ab-105">비즈니스, 엔지니어링 및 시장 계획을 개발 하기 위한 최상위 수준의 보안 프로젝트는 **프로젝트 2** , 회사 전체의 주요 직원 이라는 것이 recruited 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="1c3ab-106">연구 및 개발에 대 한 일정은 공동 작업을 효율적으로 수행 하 고 보안 모임, 진행 중인 대화 및 파일 저장을 제공 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="1c3ab-107">프로젝트 2의 결과 결과물은 비즈니스 계획, 제품 및 엔지니어링 사양, 마케팅 자료 및 일정은 Word, Excel 및 PowerPoint 파일 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="1c3ab-108">중요 한 특성으로 인해 다음과 같은 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="1c3ab-109">프로젝트 2 개 팀 구성원으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="1c3ab-110">암호화 및 보호 된 해당 파일이 보안 폴더 외부에 배포 된 경우에도 2 개 팀 구성원에만 액세스할 수 있도록 허용 하는 사용 권한으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-110">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="1c3ab-111">Contoso IT 직원은 프로젝트를 두 배로 격리 하 고 이러한 단계를 수행 하는 [팀](secure-teams-security-isolation.md) 을 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="1c3ab-112">1 단계: 비공개 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="1c3ab-112">Step 1: Created a private team</span></span>

<span data-ttu-id="1c3ab-113">먼저, Contoso IT 관리자는 팀의 기본 SharePoint 사이트에 대 한 액세스를 보호 하기 위해 [권장 되는 sharepoint 액세스 정책을](../enterprise/sharepoint-file-access-policies.md)구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="1c3ab-114">다음으로 Contoso IT 관리자가 Project 라는 새 비공개 팀을 만들고 프로젝트 2 개 직원의 사용자 계정을 구성원으로 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="1c3ab-115">구성에 대 한 자세한 내용은 [비공개 팀 만들기](secure-teams-security-isolation.md#create-a-private-team)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-115">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="1c3ab-116">2 단계: 프로젝트 2 팀에 대 한 민감도 레이블 작성</span><span class="sxs-lookup"><span data-stu-id="1c3ab-116">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="1c3ab-117">Contoso 관리자는 다음과 같은 **프로젝트별** 라는 새 민감도 레이블을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-117">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="1c3ab-118">암호화 필요</span><span class="sxs-lookup"><span data-stu-id="1c3ab-118">Requires encryption.</span></span>
- <span data-ttu-id="1c3ab-119">Microsoft 365 그룹 2 개 프로젝트에 대해 공동 작성자 권한을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-119">Allows Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>

<span data-ttu-id="1c3ab-120">원본으로 사용 하는 Project 2의 **문서** 섹션에 있는 파일은 다음과 같은 방법으로 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-120">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="1c3ab-121">사이트 사용 권한-Microsoft 365 그룹의 구성원에 대 한 액세스만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-121">The site permissions, which only allow access to members of the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="1c3ab-122">파일을 이동 하거나 복사 하는 경우 파일과 함께 이동 하는 암호화 및 사용 권한을 갖는 프로젝트 2X 민감도 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-122">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="1c3ab-123">구성에 대 한 자세한 내용은 [우편물 종류 레이블 만들기](secure-teams-security-isolation.md#create-a-sensitivity-label)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-123">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="1c3ab-124">3 단계: 기본 SharePoint 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="1c3ab-124">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="1c3ab-125">먼저, Contoso IT 관리자는 팀의 기본 SharePoint 사이트에 대 한 액세스를 보호 하기 위해 [권장 되는 sharepoint 액세스 정책을](../enterprise/sharepoint-file-access-policies.md)구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-125">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="1c3ab-126">다음으로, 프로젝트 2가 사이트 액세스를 공유 하지 못하도록 사이트에 대 한 추가 권한 설정을 구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-126">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site.</span></span> <span data-ttu-id="1c3ab-127">구성에 대 한 자세한 내용은 [보안이 격리 된 팀에 대 한 SharePoint 설정](secure-teams-security-isolation.md#sharepoint-settings)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-127">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>

<span data-ttu-id="1c3ab-128">다음은 프로젝트를 2 배로 구성 하는 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-128">Here is the resulting configuration of the Project 2X team.</span></span>

![프로젝트 2 배의 결과 구성](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="1c3ab-130">4 단계: 팀 구성원 2 대 교육 프로젝트</span><span class="sxs-lookup"><span data-stu-id="1c3ab-130">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="1c3ab-131">Contoso 보안 직원은 다음과 같은 작업을 수행 하는 필수 과정을 통해 프로젝트를 2 배의 팀 구성원에 게 교육 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-131">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="1c3ab-132">새 프로젝트에 액세스 하는 방법 2 배, 모임 및 채팅을 사용 하 고 팀 파일을 공동으로 작업 하는 방법</span><span class="sxs-lookup"><span data-stu-id="1c3ab-132">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="1c3ab-133">팀에서 새 파일을 만들고 로컬로 만든 새 파일을 업로드 하는 방법</span><span class="sxs-lookup"><span data-stu-id="1c3ab-133">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="1c3ab-134">DLP 정책이 외부에서 파일을 공유 하지 못하도록 차단 하는 방법에 대 한 데모입니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-134">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="1c3ab-135">프로젝트의 민감도 레이블을 사용 하 여 파일에 레이블을 지정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="1c3ab-135">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="1c3ab-136">프로젝트가 팀에서 나간 경우에도 파일을 2 차원으로 보호 하는 방법을 보여 주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-136">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="1c3ab-137">최종 결과는 프로젝트 2 개 팀 구성원이 대화방, 모임 및 파일을 위해 안전한 환경에서 collaborated 하는 보안 환경 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-137">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="1c3ab-138">다음은 원본으로 사용 하는 프로젝트에 저장 되는 파일의 예로, 프로젝트 2X 민감도 레이블이 지정 된 사이트를 포함 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-138">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![원본으로 사용 하는 프로젝트 2 개 사이트에 저장 된 파일의 예](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="1c3ab-140">두 개의 인스턴스에서 프로젝트 2 개 프로젝트의 보호 된 파일을 오프 라인 작업을 위해 로컬 드라이브로 다운로드 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-140">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="1c3ab-141">그러나 자격 증명을 열 때 확인 메시지가 표시 되 면 사용자가 실수로 메시지를 인식 하 고 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-141">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="1c3ab-142">팀의 공동 작업 환경 및 Microsoft 365의 보안 기능 때문에 프로젝트의 세부 정보는 프로젝트 기간 동안 기밀로 유지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-142">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="1c3ab-143">Contoso는 해당 계획을 발표 했으며, 고객 및 투자자의 안전 게 및 경쟁사의 chagrin에 새 제품 및 서비스를 배포 하는 프로세스를 진행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-143">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="1c3ab-144">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1c3ab-144">Next step</span></span>

<span data-ttu-id="1c3ab-145">조직에서 [보안 격리를 사용 하 여 팀을 배포](secure-teams-security-isolation.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c3ab-145">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

