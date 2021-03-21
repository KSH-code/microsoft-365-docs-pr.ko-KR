---
title: Advanced eDiscovery에서 AzCopy 문제 해결
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery에서 오류 수정을 위해 비 Office 365 데이터를 로드할 때 Azure AzCopy에 대한 오류를 해결합니다.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919294"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="dfd4c-103">Advanced eDiscovery에서 AzCopy 문제 해결</span><span class="sxs-lookup"><span data-stu-id="dfd4c-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="dfd4c-104">Advanced eDiscovery에서 오류 수정을 위해 Microsoft 365가 아닌 데이터 또는 문서를 로드할 때 사용자 인터페이스는 업로드할 파일이 저장되는 위치와 파일을 업로드할 Azure 저장소 위치를 포함하는 매개 변수가 포함된 Azure AzCopy 명령을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="dfd4c-105">문서를 업로드하려면 이 명령을 복사한 다음 로컬 컴퓨터의 명령 프롬프트에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="dfd4c-106">다음 스크린샷은 AzCopy 명령의 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![Microsoft 365가 아닌 파일 업로드](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="dfd4c-108">일반적으로 제공된 명령은 실행할 때 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="dfd4c-109">그러나 표시되는 명령이 성공적으로 실행되지 않는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="dfd4c-110">다음과 같은 몇 가지 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="dfd4c-111">지원되는 AzCopy 버전이 로컬 컴퓨터에 설치되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="dfd4c-112">이때 AzCopy v8.1을 사용하여 Advanced eDiscovery에서 비 Microsoft 365 데이터를 로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="dfd4c-113">이전 스크린샷에 표시된 파일 업로드 페이지에  표시되는 AzCopy 명령은 AzCopy v8.1을 사용하지 않는 경우 오류를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="dfd4c-114">이 버전을 설치하려면 Windows 에서 [AzCopy v8.1을](/previous-versions/azure/storage/storage-use-azcopy)사용하여 데이터 전송을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="dfd4c-115">AzCopy가 로컬 컴퓨터에 설치되지 않은 경우 또는 기본 위치에 설치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="dfd4c-116">AzCopy가 설치되지 않은 경우 또는 기본 설치 위치(를) 아닌 다른 위치에 설치하면 AzCopy 명령을 실행할 때 다음 오류가 표시될 `%ProgramFiles(x86)%` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

> <span data-ttu-id="dfd4c-117">시스템에서 지정된 경로를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-117">The system cannot find the path specified.</span></span>

<span data-ttu-id="dfd4c-118">로컬 컴퓨터에 AzCopy가 설치되어 있지 않은 경우 [Windows의 AzCopy v8.1을](/previous-versions/azure/storage/storage-use-azcopy)사용하여 데이터 전송에서 설치 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-118">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="dfd4c-119">기본 위치에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-119">Be sure to install it in the default location.</span></span>

<span data-ttu-id="dfd4c-120">AzCopy가 설치되지만 기본 위치가 아니라 다른 위치에 설치된 경우 명령을 복사하여 텍스트 파일에 붙여 넣은 다음 AzCopy가 설치된 위치로 경로를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-120">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="dfd4c-121">예를 들어 Azcopy가 에 있는 경우 명령의 첫 번째 부분을 에서 로 변경할 `%ProgramFiles%` 수 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-121">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="dfd4c-122">이 변경을 한 후 텍스트 파일에서 복사한 다음 명령 프롬프트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-122">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="dfd4c-123">AzCopy가 다른 위치에 설치된 경우 기본 설치 위치를 설치한 다음 기본 위치에 다시 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-123">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="dfd4c-124">이렇게 하면 향후 이 문제를 방지하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfd4c-124">This will help prevent this issue in the future.</span></span>