---
title: Contoso Corporation의 최상위 비밀 프로젝트에 대 한 격리 된 팀
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: '요약: Contoso에서 최상위 비밀 프로젝트에 대해 보안 격리를 적용 하 여 팀을 사용 하 여 새로운 제품 및 서비스 제품군을 개발 하는 방법을 설명 합니다.'
ms.openlocfilehash: ba9a66d2419e81aeb1eac026b16c0475ac6d0614
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778595"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="b4e95-103">Contoso Corporation의 최상위 비밀 프로젝트에 대 한 격리 된 팀</span><span class="sxs-lookup"><span data-stu-id="b4e95-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="b4e95-104">경영진은이 Contoso의 CEO가 향후 5 년 동안 Contoso의 이익을 두 배로 만들 수 있는 새로운 제품 및 서비스 제품군의 개발을 주문 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="b4e95-105">비즈니스, 엔지니어링 및 시장 계획을 개발 하기 위한 최상위 수준의 보안 프로젝트는 **프로젝트 2** , 회사 전체의 주요 직원 이라는 것이 recruited 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="b4e95-106">연구 및 개발에 대 한 일정은 공동 작업을 효율적으로 수행 하 고 보안 모임, 진행 중인 대화 및 파일 저장을 제공 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="b4e95-107">프로젝트 2의 결과 결과물은 비즈니스 계획, 제품 및 엔지니어링 사양, 마케팅 자료 및 일정은 Word, Excel 및 PowerPoint 파일 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="b4e95-108">중요 한 특성으로 인해 다음과 같은 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="b4e95-109">프로젝트 2, 팀 구성원 및 선임 리더십으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="b4e95-110">암호화 및 보호 됨 해당 파일이 보안 폴더 외부에 배포 된 경우에도 프로젝트 2 개 팀 구성원 및 선임 리더십에만 액세스할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="b4e95-111">Contoso IT 직원은 프로젝트를 두 배로 격리 하 고 이러한 단계를 수행 하는 [팀](secure-teams-security-isolation.md) 을 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="b4e95-112">1 단계: 비공개 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="b4e95-112">Step 1: Created a private team</span></span>

<span data-ttu-id="b4e95-113">먼저, Contoso IT 관리자는 팀의 기본 SharePoint 사이트에 대 한 액세스를 보호 하기 위해 [권장 되는 sharepoint 액세스 정책을](../enterprise/sharepoint-file-access-policies.md)구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="b4e95-114">다음으로 Contoso IT 관리자가 Project 라는 새 비공개 팀을 만들고 프로젝트 2 개 직원의 사용자 계정을 구성원으로 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="b4e95-115">또한 프로젝트 2 배의 팀 소유자만 개인 채널을 만들 수 있도록 팀을 구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="b4e95-116">구성에 대 한 자세한 내용은 [비공개 팀 만들기](secure-teams-security-isolation.md#create-a-private-team)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4e95-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="b4e95-117">2 단계: 프로젝트 2 팀에 대 한 민감도 레이블 작성</span><span class="sxs-lookup"><span data-stu-id="b4e95-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="b4e95-118">Contoso 관리자는 다음과 같은 **프로젝트별** 라는 새 민감도 레이블을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="b4e95-119">암호화를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-119">Enabled encryption.</span></span>
- <span data-ttu-id="b4e95-120">Microsoft 365 그룹 2 개 프로젝트에 대해 공동 작성자 권한을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="b4e95-121">선임 리더십 그룹에 대 한 뷰어 권한이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="b4e95-122">관리 되지 않는 장치에 대 한 액세스 차단</span><span class="sxs-lookup"><span data-stu-id="b4e95-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="b4e95-123">원본으로 사용 하는 Project 2의 **문서** 섹션에 있는 파일은 다음과 같은 방법으로 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="b4e95-124">Microsoft 365 그룹의 구성원에 대 한 모든 권한 및 선임 리더십 그룹에 대 한 읽기 권한을 허용 하는 사이트 권한</span><span class="sxs-lookup"><span data-stu-id="b4e95-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="b4e95-125">파일을 이동 하거나 복사 하는 경우 파일과 함께 이동 하는 암호화 및 사용 권한을 갖는 프로젝트 2X 민감도 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="b4e95-126">구성에 대 한 자세한 내용은 [우편물 종류 레이블 만들기](secure-teams-security-isolation.md#create-a-sensitivity-label)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4e95-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="b4e95-127">3 단계: 기본 SharePoint 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="b4e95-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="b4e95-128">먼저, Contoso IT 관리자는 팀의 기본 SharePoint 사이트에 대 한 액세스를 보호 하기 위해 [권장 되는 sharepoint 액세스 정책을](../enterprise/sharepoint-file-access-policies.md)구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="b4e95-129">다음으로, 사이트에 대 한 추가 사용 권한 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="b4e95-130">Project에서 그룹 구성원이 사이트에 대 한 액세스를 공유 하지 못하도록 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="b4e95-131">구성에 대 한 자세한 내용은 [보안이 격리 된 팀에 대 한 SharePoint 설정](secure-teams-security-isolation.md#sharepoint-settings)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b4e95-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="b4e95-132">선임 리더십 그룹에 대 한 읽기 권한</span><span class="sxs-lookup"><span data-stu-id="b4e95-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="b4e95-133">다음으로, 프로젝트 그룹 구성원이 사이트에 대 한 액세스를 공유 하는 것을 방지 하기 위해 사이트에 대 한 추가 권한 설정을 구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="b4e95-134">프로젝트의 개인 채널이 2 배로 만들어진 후 그룹 소유자가 게스트 공유를 사용 하지 않도록 설정 하 고, **특정 사용자** 값에 대 한 기본 공유 링크를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="b4e95-135">다음은 보안이 격리 된 프로젝트를 2 배로 구성 하는 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![프로젝트 2 배의 결과 구성](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="b4e95-137">4 단계: 팀 구성원 2 대 교육 프로젝트</span><span class="sxs-lookup"><span data-stu-id="b4e95-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="b4e95-138">Contoso 보안 직원은 다음과 같은 작업을 수행 하는 필수 과정을 통해 프로젝트를 2 배의 팀 구성원에 게 교육 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="b4e95-139">새 프로젝트에 액세스 하는 방법 2 배, 모임 및 채팅을 사용 하 고 팀 파일을 공동으로 작업 하는 방법</span><span class="sxs-lookup"><span data-stu-id="b4e95-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="b4e95-140">팀에서 새 파일을 만들고 로컬로 만든 새 파일을 업로드 하는 방법</span><span class="sxs-lookup"><span data-stu-id="b4e95-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="b4e95-141">프로젝트의 민감도 레이블을 사용 하 여 파일에 레이블을 지정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="b4e95-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="b4e95-142">프로젝트가 팀에서 나간 경우에도 파일을 2 차원으로 보호 하는 방법을 보여 주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="b4e95-143">최종 결과는 프로젝트 2 개 팀 구성원이 대화방, 모임 및 파일을 위해 안전한 환경에서 collaborated 하는 보안 환경 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="b4e95-144">다음은 원본으로 사용 하는 프로젝트에 저장 되는 파일의 예로, 프로젝트 2X 민감도 레이블이 지정 된 사이트를 포함 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![원본으로 사용 하는 프로젝트 2 개 사이트에 저장 된 파일의 예](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="b4e95-146">두 개의 인스턴스에서 프로젝트 2 개 프로젝트의 보호 된 파일을 오프 라인 작업을 위해 로컬 드라이브로 다운로드 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="b4e95-147">그러나 자격 증명을 열 때 확인 메시지가 표시 되 면 사용자가 실수로 메시지를 인식 하 고 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="b4e95-148">팀의 공동 작업 환경 및 Microsoft 365의 보안 기능 때문에 프로젝트의 세부 정보는 프로젝트 기간 동안 기밀로 유지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="b4e95-149">Contoso는 해당 계획을 발표 했으며, 고객 및 투자자의 안전 게 및 경쟁사의 chagrin에 새 제품 및 서비스를 배포 하는 프로세스를 진행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="b4e95-150">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b4e95-150">Next step</span></span>

<span data-ttu-id="b4e95-151">조직에서 [보안 격리를 사용 하 여 팀을 배포](secure-teams-security-isolation.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e95-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

