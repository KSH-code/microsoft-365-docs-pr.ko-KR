---
title: 데이터 조사에 대 한 사용 권한 할당 (미리 보기)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 이 문서에서는 Microsoft 365에서 데이터 조사 도구를 사용 하는 데 필요한 사용 권한을 설정 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: 85a800c3e21c270f46de78bdef77d7b7a98e0eca
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285444"
---
# <a name="assign-permissions-for-data-investigations-preview"></a><span data-ttu-id="5d8f6-103">데이터 조사에 대 한 사용 권한 할당 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="5d8f6-103">Assign permissions for Data Investigations (preview)</span></span>

<span data-ttu-id="5d8f6-104">Office 365 또는 Microsoft 365 준수 센터의 데이터 조사에 액세스 하려면 Data Investigator 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d8f6-104">To access a data investigation in the Office 365 or Microsoft 365 compliance center, you need be a member of the Data Investigator role group.</span></span> <span data-ttu-id="5d8f6-105">역할 그룹에 구성원을 추가 하려면 조직 관리 역할 그룹의 구성원 이거나 보안 & 준수 센터에서 역할 관리 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d8f6-105">To add members to a role group, you must be a member of the Organization Management role group or assigned the Role Management role in the Security & Compliance Center.</span></span> <span data-ttu-id="5d8f6-106">사용자가 Data Investigator 역할 그룹의 구성원이 된 후에는 구성원 인 데이터 조사에서이를 만들고, 액세스 하 고, 조사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d8f6-106">After a user becomes a member of the Data Investigator role group, they can create, access, and conduct investigations in the data investigations that you are a member of.</span></span>

<span data-ttu-id="5d8f6-107">데이터 조사 권한을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="5d8f6-107">To assign data investigations permissions:</span></span>

1. <span data-ttu-id="5d8f6-108">으로 이동 하 [https://protection.office.com](https://protection.office.com) 고 조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d8f6-108">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="5d8f6-109">보안 & 준수 센터에서 **사용 권한을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d8f6-109">In the Security & Compliance Center, click **Permissions**.</span></span>

3. <span data-ttu-id="5d8f6-110">**데이터 Investigator** 역할 그룹을 클릭 하 고 플라이 아웃 페이지의 **구성원** 옆에 있는 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d8f6-110">Click the **Data Investigator** role group, and then next to **Members** on the flyout page, click **Edit**.</span></span>

4. <span data-ttu-id="5d8f6-111">**구성원 선택을** 클릭 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d8f6-111">Click **Choose members** and then click **Add**.</span></span> <span data-ttu-id="5d8f6-112">데이터 investigators 추가 하려는 사용자를 선택 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d8f6-112">Select the users that you want to add as data investigators, and then click **Add**.</span></span>

5. <span data-ttu-id="5d8f6-113">모든 사용자를 추가한 후에 **완료** 를 클릭 하 고 **저장** 을 클릭 하 여 역할 그룹에 대 한 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d8f6-113">After you've added all the users, click **Done** and then click **Save** to save the changes to the role group.</span></span>

> [!NOTE]
> <span data-ttu-id="5d8f6-114">Data Investigator 역할 그룹에 할당 된 데이터 조사 관리 역할은 Office 365 또는 Microsoft 365 준수 센터의 데이터 조사 도구에 액세스 하는 데 필요한 권한을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d8f6-114">The Data Investigation Management role that is assigned to the Data Investigator role group provides the necessary permissions to access the Data Investigations tool in the Office 365 or Microsoft 365 compliance center.</span></span> <span data-ttu-id="5d8f6-115">기본적으로이 역할은 조직 관리 역할 그룹에 할당 되지 않으므로 조직의 전역 관리자가 기본적으로 데이터 조사 도구에 액세스 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d8f6-115">By default, this role is not assigned to the Organization Management role group, which means that global admins in your organization may not be able to access the Data Investigations tool by default.</span></span> <span data-ttu-id="5d8f6-116">이 문제를 해결 하려면 global admins를 Data Investigator 역할 그룹에 추가 하거나 조직 관리 역할 그룹에 데이터 조사 관리 역할을 추가 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d8f6-116">To fix this, you can add global admins to the Data Investigator role group or add the Data Investigation Management role to the Organization Management role group.</span></span> <span data-ttu-id="5d8f6-117">세 번째 옵션은 사용자 지정 역할 그룹을 만들고 데이터 조사 관리 역할 및 기타 역할을 할당 한 다음 적절 한 구성원을 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5d8f6-117">A third option would be to create a custom role group and assign the Data Investigation Management role (and other roles) and then add appropriate members.</span></span> <span data-ttu-id="5d8f6-118">역할 그룹 및 역할에 대 한 자세한 내용은 [Security & 준수 센터의 사용 권한을](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d8f6-118">For more information about role groups and roles, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>
