---
title: Contoso Corporation의 최상위 프로젝트를 위한 격리된 팀
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: '요약: Contoso가 비밀 프로젝트를 위해 보안이 강화된 팀을 사용하여 새 제품 및 서비스 제품군을 개발하는 방법을 설명하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 751bf3972d148219a6cc341067c0bf34cd581447
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029019"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="dabf1-103">Contoso Corporation의 최상위 프로젝트를 위한 격리된 팀</span><span class="sxs-lookup"><span data-stu-id="dabf1-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="dabf1-104">임원진 오프사이트 이후, Contoso의 CEO는 다음 5년 동안 Contoso의 이익을 두 배로 증가할 수 있는 새로운 제품군의 제품 및 서비스 개발을 주문했습니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="dabf1-105">비즈니스, 엔지니어링 및 시장 계획을 개발하기 위한 최고의 비밀 프로젝트는 Project **2X로** 이름이 지정되고 회사 전체의 주요 직원을 모집했습니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="dabf1-106">연구 및 개발 일정이 협조적이기 때문에 공동 작업을 효율적으로 진행하고 안전한 모임, 지속적인 대화 및 파일 저장소를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="dabf1-107">이러한 결과로 Project 2X의 결과물은 Word, Excel 및 PowerPoint 파일 형식의 비즈니스 계획, 제품 및 엔지니어링 사양, 마케팅 자료 및 일정입니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="dabf1-108">중요한 특성으로 인해 이러한 파일에 대한 액세스는 다음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="dabf1-109">2X Project 수석 리더십으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="dabf1-110">파일이 보안 폴더 외부에 배포된 경우에도 2X 팀 Project 고위 임원만 액세스할 수 있도록 권한이 암호화되고 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="dabf1-111">Contoso IT 직원은 2X 및 Project 보안이 있는 팀을 사용했습니다. [](secure-teams-security-isolation.md)</span><span class="sxs-lookup"><span data-stu-id="dabf1-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="dabf1-112">1단계: 비공개 팀 생성</span><span class="sxs-lookup"><span data-stu-id="dabf1-112">Step 1: Created a private team</span></span>

<span data-ttu-id="dabf1-113">먼저, 팀의 기본 SharePoint 사이트에 대한 액세스를 보호하기 위해 Contoso IT 관리자는 권장되는 액세스 SharePoint [구성했습니다.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="dabf1-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="dabf1-114">다음으로, Contoso IT 관리자가 Project 2X라는 새 개인 팀을 만든 다음 Project 2X 직원의 사용자 계정을 구성원으로 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="dabf1-115">또한 2X 팀 소유자만 비공개 채널을 Project 수 있도록 팀을 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="dabf1-116">구성 세부 정보는 비공개 팀 [만들기를 참조합니다.](secure-teams-security-isolation.md#create-a-private-team)</span><span class="sxs-lookup"><span data-stu-id="dabf1-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="dabf1-117">2단계: Project 2X 팀에 대한 민감도 레이블 생성</span><span class="sxs-lookup"><span data-stu-id="dabf1-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="dabf1-118">Contoso 관리자는 **2X라는** 새 Project 레이블을 만들었다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="dabf1-119">암호화를 사용하도록 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-119">Enabled encryption.</span></span>
- <span data-ttu-id="dabf1-120">2X Co-Author 2X 그룹에 Project 권한을 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="dabf1-121">Senior Leadership 그룹에 대한 보기 권한 허용</span><span class="sxs-lookup"><span data-stu-id="dabf1-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="dabf1-122">관리되지 않는 장치에 대한 액세스가 차단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="dabf1-123">기본 2X Project 문서 섹션의 SharePoint 다음을 통해 보호됩니다. </span><span class="sxs-lookup"><span data-stu-id="dabf1-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="dabf1-124">사이트 사용 권한 - Project 2X 그룹의 구성원에게만 모든 Microsoft 365 권한 및 Senior Leadership 그룹에 대한 읽기 권한만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="dabf1-125">이 Project 이동하거나 사이트에서 복사하는 경우 파일과 함께 이동하는 암호화 및 사용 권한이 있는 2X 민감도 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="dabf1-126">구성 세부 정보는 민감도 레이블 [만들기를 참조합니다.](secure-teams-security-isolation.md#create-a-sensitivity-label)</span><span class="sxs-lookup"><span data-stu-id="dabf1-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="dabf1-127">3단계: 기본 사이트 SharePoint 구성</span><span class="sxs-lookup"><span data-stu-id="dabf1-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="dabf1-128">먼저, 팀의 기본 SharePoint 사이트에 대한 액세스를 보호하기 위해 Contoso IT 관리자는 권장되는 액세스 SharePoint [구성했습니다.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="dabf1-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="dabf1-129">다음으로 사이트에 대한 추가 사용 권한 설정을 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="dabf1-130">2X Project 구성원이 사이트에 대한 액세스를 공유하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="dabf1-131">구성 세부 정보는 보안 SharePoint 팀에 대한 설정 [설정을 참조하세요.](secure-teams-security-isolation.md#sharepoint-settings)</span><span class="sxs-lookup"><span data-stu-id="dabf1-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="dabf1-132">선임 리더십 그룹에 대한 읽기 권한</span><span class="sxs-lookup"><span data-stu-id="dabf1-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="dabf1-133">그런 다음 2X 그룹 구성원이 사이트에 대한 액세스를 공유하지 못하도록 Project 추가 권한 설정을 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="dabf1-134">2X에 대한 비공개 채널이 Project 그룹 소유자가 게스트 공유를 사용하지 않도록 설정하고 기본 공유 링크를 **특정** 사용자 값으로 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="dabf1-135">다음은 보안이 Project 2X 팀의 결과 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![2X 팀의 결과 Project 구성](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="dabf1-137">4단계: 교육된 Project 2X 팀 구성원</span><span class="sxs-lookup"><span data-stu-id="dabf1-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="dabf1-138">Contoso 보안 직원은 다음을 Project 필수 과정에 2X 팀 구성원을 교육했습니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="dabf1-139">새 2X Project 액세스하고, 모임 및 채팅을 사용하며, 팀 파일을 공동으로 작업하는 방법</span><span class="sxs-lookup"><span data-stu-id="dabf1-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="dabf1-140">팀에서 새 파일을 만들고 로컬에서 만든 새 파일을 업로드하는 방법</span><span class="sxs-lookup"><span data-stu-id="dabf1-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="dabf1-141">2X 민감도 레이블을 Project 레이블을 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="dabf1-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="dabf1-142">2X 레이블이 팀을 떠날 Project 2X 레이블이 파일을 보호하는 방법에 대한 데모입니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="dabf1-143">최종적으로는 2X 팀 구성원이 채팅Project 모임 및 파일을 위한 안전한 환경에서 공동 작업을 하는 안전한 환경이되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="dabf1-144">다음은 2X 민감도 레이블이 할당된 Project 2X 사이트에 Project 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![2X 사이트에 저장된 파일의 Project 예](../media/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="dabf1-146">몇 가지 경우에 Project 2X 팀 구성원이 오프라인 작업을 위해 Project 2X 레이블로 보호된 파일을 로컬 드라이브에 다운로드했습니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="dabf1-147">그러나 자격 증명을 열 때 자격 증명을 입력하라는 메시지가 표시되면 실수를 실현하고 삭제했습니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="dabf1-148">Teams 환경과 Microsoft 365 기능 때문에 Project 2X의 세부 정보는 프로젝트 기간 동안 비밀로 유지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="dabf1-149">Contoso는 계획을 발표하고 고객 및 투자가의 즐거움과 경쟁업체를 위해 새로운 제품 및 서비스를 출시하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="dabf1-150">다음 단계</span><span class="sxs-lookup"><span data-stu-id="dabf1-150">Next step</span></span>

<span data-ttu-id="dabf1-151">[조직에 보안이 고지된](secure-teams-security-isolation.md) 팀을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="dabf1-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

