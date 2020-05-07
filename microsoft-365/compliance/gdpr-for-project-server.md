---
title: Project Server GDPR
description: 온-프레미스 Project Server에서 유럽 연합 일반 개인정보보호법(GDPR) 요구 사항을 해결하는 방법을 알아봅니다.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3a7eb291d0da72adf171594aac307ec0ad91829d
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036241"
---
# <a name="gdpr-for-project-server"></a><span data-ttu-id="44e19-103">Project Server GDPR</span><span class="sxs-lookup"><span data-stu-id="44e19-103">GDPR for Project Server</span></span>

<span data-ttu-id="44e19-p101">Project Server는 사용자 지정 스크립트를 사용하여 Project Web App에서 사용자 데이터를 내보내고 수정합니다. 기본 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44e19-p101">Project Server uses custom scripts to export and redact user data in Project Web App. The basic process is:</span></span>

1.  <span data-ttu-id="44e19-106">팜에서 Project Web App 사이트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="44e19-106">Find the Project Web App sites in your farm.</span></span>

2.  <span data-ttu-id="44e19-107">사용자를 포함하는 각 사이트에서 프로젝트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="44e19-107">Find the projects in each site that contain the user.</span></span>

3.  <span data-ttu-id="44e19-108">검토할 데이터 형식을 내보내고 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="44e19-108">Export and review the types of data that you want to review.</span></span>

4.  <span data-ttu-id="44e19-109">필요에 따라 데이터를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="44e19-109">Redact data as needed.</span></span>

<span data-ttu-id="44e19-110">이러한 단계는 아래 문서에 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e19-110">These steps are covered in detail in the following articles:</span></span>

- [<span data-ttu-id="44e19-111">Project Server에서 사용자 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="44e19-111">Export user data from Project Server</span></span>](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [<span data-ttu-id="44e19-112">Project Server에서 사용자 데이터 삭제</span><span class="sxs-lookup"><span data-stu-id="44e19-112">Delete user data from Project Server</span></span>](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


<span data-ttu-id="44e19-p102">Project Server는 SharePoint Server와 SharePoint ULS 및 사용 현황 데이터베이스에 대한 로그 이벤트를 기반으로 구축되었습니다. 자세한 내용은 [SharePoint Server에 대한 GDPR](gdpr-for-sharepoint-server.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44e19-p102">Note that Project Server is built on top of SharePoint Server and logs events to the SharePoint ULS logs and Usage database. See [GDPR for SharePoint Server](gdpr-for-sharepoint-server.md) for more information.</span></span>
