---
title: Microsoft 제품이 아닌 365 데이터를 증거에 로드
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
description: Office 이외 365 콘텐츠 가져오기 기능을 사용 하 여 Office 이외 365 문서를 데이터 조사의 증거에 업로드 하는 방법을 알아봅니다.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: b6d8c2f65a1fa3a43fa2ac4bf3821cc6c1fac514
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285374"
---
# <a name="load-non-microsoft-365-data-into-evidence"></a><span data-ttu-id="0cda0-103">Microsoft 제품이 아닌 365 데이터를 증거에 로드</span><span class="sxs-lookup"><span data-stu-id="0cda0-103">Load non-Microsoft 365 data into evidence</span></span>

<span data-ttu-id="0cda0-104">데이터 조사에서 분석을 수행 하는 데 필요한 모든 문서는 Microsoft 365에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-104">Not all documents that you may need to analyze in a data investigation will be located in Microsoft 365.</span></span> <span data-ttu-id="0cda0-105">비 Microsoft 365 콘텐츠 가져오기 기능을 사용 하 여 Microsoft 365에 없는 문서를 데이터 조사에서 분석할 수 있도록 증거에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-105">With the Non-Microsoft 365 content import feature you can upload documents that don't live in Microsoft 365 into evidence so they can be analyzed in a data investigation.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="0cda0-106">Office 이외의 365 콘텐츠를 업로드 하기 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0cda0-106">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="0cda0-107">이 절차에 설명 된 것 처럼 365 Microsoft 제품이 아닌 업로드 기능을 사용 하려면 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-107">Using the upload Non-Microsoft 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="0cda0-108">Microsoft 365 또는 Office 365 E5 구독</span><span class="sxs-lookup"><span data-stu-id="0cda0-108">A Microsoft 365 or Office 365 E5 subscription.</span></span>

- <span data-ttu-id="0cda0-109">비 Microsoft 365 콘텐츠가 업로드 될 모든 사용자에 게는 해당 E5 또는 E5 추가 기능 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-109">All people of interest whose non-Microsoft 365 content will be uploaded must have the appropriate E5 or E5 add-on license.</span></span>

- <span data-ttu-id="0cda0-110">기존 eDiscovery 사례</span><span class="sxs-lookup"><span data-stu-id="0cda0-110">An existing eDiscovery case.</span></span>

- <span data-ttu-id="0cda0-111">업로드 하기 위한 모든 파일은 custodian 당 하나의 폴더가 있고 폴더 이름이이 형식 *alias@domainname*으로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-111">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname*.</span></span> <span data-ttu-id="0cda0-112">*Alias@domainname* 사용자의 별칭 및 도메인 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-112">The *alias@domainname* must be user's alias and domain.</span></span> <span data-ttu-id="0cda0-113">모든 *alias@domainname* 폴더를 루트 폴더로 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-113">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="0cda0-114">루트 폴더에는 *alias@domainname* 폴더만 포함할 수 있으며 루트 폴더에는 느슨한 파일이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-114">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="0cda0-115">비 Microsoft 365 콘텐츠 폴더 구조에 대 한 액세스 권한이 있는 컴퓨터에 eDiscovery 관리자 또는 eDiscovery 관리자 Microsoft Azure Storage Tools가 설치 되어 있는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-115">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span>

- <span data-ttu-id="0cda0-116">[AzCopy을 사용 하 여 시작할](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)수 있는 AzCopy을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-116">Install AzCopy, which you can do from [Get started with AzCopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span>

## <a name="upload-non-microsoft-365-content-in-to-a-data-investigation"></a><span data-ttu-id="0cda0-117">Microsoft 제품이 아닌 365 콘텐츠를 데이터 조사에 업로드</span><span class="sxs-lookup"><span data-stu-id="0cda0-117">Upload non-Microsoft 365 content in to a data investigation</span></span>

1. <span data-ttu-id="0cda0-118">**데이터 조사** 를 열고 Microsoft 제품이 아닌 365 데이터를 업로드할 조사로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-118">Open **Data Investigations** and go to the investigation that the non-Microsoft 365 data will be uploaded to.</span></span>  <span data-ttu-id="0cda0-119">**증거** 탭을 클릭 한 다음 데이터를 로드할 증거 세트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-119">Click the **Evidence** tab, then select the evidence set you wish to load the data to.</span></span>  <span data-ttu-id="0cda0-120">증명 정보 집합을 아직 만들지 않은 경우 지금 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-120">If you have not already created an evidence set, you can do so now.</span></span>  <span data-ttu-id="0cda0-121">마지막으로 **증거 관리** 를 클릭 하 고 데이터 섹션에서 **업로드를 확인** 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-121">Finally, click **Manage evidence** then **View uploads** in the data section</span></span>

2. <span data-ttu-id="0cda0-122">**파일 업로드** 단추를 클릭 하 여 Microsoft 제품이 아닌 365 데이터 가져오기 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-122">Click the **Upload files** button to start the Non-Microsoft 365 data import wizard.</span></span>

![파일 업로드](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="0cda0-124">마법사의 첫 번째 단계에서는 업로드할 파일에 대 한 안전한 Azure blob만 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-124">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="0cda0-125">준비가 완료 되 면 **다음: 파일 업로드** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-125">After the preparation is complete, click the **Next: Upload files** button.</span></span>

![비 Microsoft 365 데이터 가져오기 준비](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="0cda0-127">**파일 업로드** 단계에서 **파일의 위치에 대 한 경로**를 지정 합니다. 여기서는 가져오기에 사용할 Microsoft 365이 아닌 데이터를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-127">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Microsoft 365 data you plan on importing is located.</span></span>  <span data-ttu-id="0cda0-128">올바른 위치를 설정 하면 AzCopy 명령이 제대로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-128">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="0cda0-129">AzCopy을 아직 설치 하지 않은 경우 여기에서이 작업을 수행할 수 있습니다. https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="0cda0-129">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="0cda0-130">**클립보드에 복사** 링크를 클릭 하 여 미리 정의 된 명령을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-130">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="0cda0-131">Windows 명령 프롬프트를 시작 하 고 명령을 붙여 넣은 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-131">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="0cda0-132">파일이 보안 Azure blob 저장소에 업로드 되 고 다음 단계를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-132">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![비 Microsoft 365 데이터 가져오기를 위한 파일 업로드](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![AzCopy을 사용 하 여 Microsoft 제품이 아닌 365 데이터 가져오기](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="0cda0-135">마지막으로 보안 & 준수로 돌아간 **다음: 프로세스 파일** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-135">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="0cda0-136">이렇게 하면 업로드 된 파일의 처리, 텍스트 추출 및 인덱싱이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-136">This initiates processing, text extraction, and indexing of the uploaded files.</span></span>  <span data-ttu-id="0cda0-137">여기에서 처리의 진행 상황과 **작업** 탭을 추적할 수 있습니다.  완료 되 면 새 파일을 증거 집합에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-137">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files are available in the evidence set.</span></span>  <span data-ttu-id="0cda0-138">처리가 완료 되 면 마법사를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cda0-138">After processing is complete, you can dismiss the wizard.</span></span>

![타사 365 가져오기 프로세스 파일](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

