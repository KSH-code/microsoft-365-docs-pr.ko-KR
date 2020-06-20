---
title: Advanced eDiscovery에서 AzCopy 문제 해결
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery에서 오류 수정을 위해 비 Office 365 데이터를 로드할 때 Azure AzCopy의 오류를 해결 합니다.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 0185c179039b7aec72bc400709225ef42489f620
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819148"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="5aec8-103">Advanced eDiscovery에서 AzCopy 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5aec8-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="5aec8-104">고급 eDiscovery에서 오류 수정을 위해 Microsoft가 아닌 365 데이터 또는 문서를 로드할 때 사용자 인터페이스는 업로드 하려는 파일이 저장 되는 위치 및 파일이 업로드 될 Azure 저장 위치와 함께 매개 변수가 포함 된 Azure AzCopy 명령을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="5aec8-105">문서를 업로드 하려면 로컬 컴퓨터의 명령 프롬프트에서이 명령을 복사한 다음 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="5aec8-106">다음 스크린샷에는 AzCopy 명령의 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![타사 365 파일 업로드](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="5aec8-108">일반적으로 제공 되는 명령은 실행할 때 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="5aec8-109">그러나 표시 된 명령이 정상적으로 실행 되지 않는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="5aec8-110">몇 가지 가능한 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="5aec8-111">지원 되는 AzCopy 버전은 로컬 컴퓨터에 설치 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="5aec8-112">이 경우에는 AzCopy v 8.1을 사용 하 여 고급 eDiscovery에서 Microsoft가 아닌 365 데이터를 로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="5aec8-113">이전 스크린샷에 표시 된 **파일 업로드** 페이지에 표시 되는 AzCopy 명령은 AzCopy v 8.1을 사용 하지 않는 경우 오류를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="5aec8-114">이 버전을 설치 하려면 [Windows의 AzCopy v 8.1을 사용 하 여 데이터 전송을](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5aec8-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="5aec8-115">AzCopy가 로컬 컴퓨터에 설치 되어 있지 않거나 기본 위치에 설치 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="5aec8-116">AzCopy가 설치 되어 있지 않거나 기본 설치 위치 (is) 이외의 위치에 설치 되어 있는 경우 `%ProgramFiles(x86)%` AzCopy 명령을 실행 하면 다음 오류 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

    The system cannot find the path specified.

<span data-ttu-id="5aec8-117">AzCopy가 로컬 컴퓨터에 설치 되어 있지 않은 경우 [Windows의 AzCopy v 8.1을 사용 하 여 전송 데이터](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)에서 설치 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-117">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="5aec8-118">기본 위치에 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-118">Be sure to install it in the default location.</span></span>

<span data-ttu-id="5aec8-119">AzCopy가 설치 되어 있지만 기본 위치와 다른 위치에 설치 되어 있는 경우 명령을 복사 하 여 텍스트 파일에 붙여 넣은 다음 AzCopy가 설치 된 위치에 대 한 경로를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-119">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="5aec8-120">예를 들어 Azcopy가에 있는 경우 `%ProgramFiles%` 명령의 첫 번째 부분을로 변경할 수 있습니다 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` .</span><span class="sxs-lookup"><span data-stu-id="5aec8-120">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="5aec8-121">이 변경 작업을 수행한 후에는 텍스트 파일에서 복사한 다음 명령 프롬프트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-121">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="5aec8-122">기본 설치 위치 이외의 위치에 AzCopy가 설치 되어 있으면 제거한 다음 기본 위치에 다시 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-122">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="5aec8-123">이를 통해 나중에이 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5aec8-123">This will help prevent this issue in the future.</span></span>
