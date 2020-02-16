---
title: 비 Office 365 데이터를 증거에 로드
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
description: ''
ms.openlocfilehash: 4db0b40d485c4c1107bdcb0d49616cadb15b1915
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072181"
---
# <a name="load-non-office-365-data-into-evidence"></a><span data-ttu-id="97d76-102">비 Office 365 데이터를 증거에 로드</span><span class="sxs-lookup"><span data-stu-id="97d76-102">Load non-Office 365 data into evidence</span></span>

<span data-ttu-id="97d76-103">데이터 조사에서 분석을 수행 하는 데 필요한 모든 문서는 Office 365에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-103">Not all documents that you may need to analyze in a data investigation will be located in Office 365.</span></span> <span data-ttu-id="97d76-104">Office가 아닌 365 콘텐츠 가져오기 기능을 사용 하 여 Office 365에 없는 문서를 데이터 조사에서 분석할 수 있도록 증거에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-104">With the Non-Office 365 content import feature you can upload documents that don't live in Office 365 into evidence so they can be analyzed in a data investigation.</span></span>

>[!Note]
><span data-ttu-id="97d76-105">데이터를 조사 하려면 고급 준수 추가 기능 또는 조직에 대 한 E5 구독을 포함 하는 Office 365 E3이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-105">Data investigation requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="97d76-106">고급 eDiscovery를 만들려고 하는 계획이 없는 경우 Office 365 Enterprise E5의 평가판에 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-106">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="97d76-107">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="97d76-107">Before you begin</span></span>

<span data-ttu-id="97d76-108">이 절차에 설명 된 대로 Office 이외에 업로드 365 기능을 사용 하려면 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-108">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="97d76-109">고급 규정 준수 추가 기능 또는 E5 구독을 포함 하는 Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="97d76-109">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="97d76-110">비 Office 365 콘텐츠가 업로드 되는 모든 custodians에는 고급 규정 준수 추가 기능 또는 E5 라이선스가 포함 된 E3이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-110">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="97d76-111">기존 eDiscovery 사례</span><span class="sxs-lookup"><span data-stu-id="97d76-111">An existing eDiscovery case.</span></span>

- <span data-ttu-id="97d76-112">업로드 하기 위한 모든 파일은 custodian 당 하나의 폴더가 있고 폴더 이름이이 형식 *alias@domainname*으로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-112">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname*.</span></span> <span data-ttu-id="97d76-113">*Alias@domainname* 사용자의 Office 365 별칭과 domain 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-113">The *alias@domainname* must be users Office 365 alias and domain.</span></span> <span data-ttu-id="97d76-114">모든 *alias@domainname* 폴더를 루트 폴더로 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-114">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="97d76-115">루트 폴더에는 *alias@domainname* 폴더만 포함할 수 있으며 루트 폴더에는 느슨한 파일이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-115">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="97d76-116">비 Office 365 콘텐츠 폴더 구조에 대 한 액세스 권한이 있는 컴퓨터에 eDiscovery 관리자 또는 eDiscovery 관리자 Microsoft Azure Storage Tools가 설치 되어 있는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-116">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="97d76-117">다음에서 수행할 수 있는 AzCopy을 설치 합니다.https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="97d76-117">Install AzCopy, which you can do from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-in-to-a-data-investigation"></a><span data-ttu-id="97d76-118">Office 이외 365 콘텐츠를 데이터 조사에 업로드</span><span class="sxs-lookup"><span data-stu-id="97d76-118">Upload non-Office 365 content in to a data investigation</span></span>

1. <span data-ttu-id="97d76-119">\* \* \* \* 데이터 조사 \* \*를 연 다음 비 Office 365 데이터가 업로드 될 조사를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-119">Open \*\*\*\*Data Investigations\*\*, then the investigation that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="97d76-120">**증거 자료** 탭을 클릭 한 다음 비 Office 365 데이터를 로드할 증거를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-120">Click the **Evidence** tab, then select the evidence set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="97d76-121">증명 정보 집합을 아직 만들지 않은 경우 지금 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-121">If you have not already created an evidence set, you can do so now.</span></span>  <span data-ttu-id="97d76-122">마지막으로 **증거 관리** 를 클릭 하 고 비 Office 365 데이터 섹션에서 **업로드를 확인** 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-122">Finally, click **Manage evidence** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="97d76-123">**파일 업로드** 단추를 클릭 하 여 비 Office 365 데이터 가져오기 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-123">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![파일 업로드](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="97d76-125">마법사의 첫 번째 단계에서는 업로드할 파일에 대 한 안전한 Azure blob만 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-125">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="97d76-126">준비가 완료 되 면 **다음: 파일 업로드** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-126">After the preparation is complete, click the **Next: Upload files** button.</span></span>

![Office가 아닌 365 데이터 가져오기 준비](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="97d76-128">**파일 업로드** 단계에서 **파일의 위치에 대 한 경로**를 지정 합니다. 여기서는 가져오기에 사용 하는 비 Office 365 데이터가 있는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-128">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="97d76-129">올바른 위치를 설정 하면 AzCopy 명령이 제대로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-129">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="97d76-130">AzCopy을 아직 설치 하지 않은 경우 여기에서이 작업을 수행할 수 있습니다.https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="97d76-130">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="97d76-131">**클립보드에 복사** 링크를 클릭 하 여 미리 정의 된 명령을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-131">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="97d76-132">Windows 명령 프롬프트를 시작 하 고 명령을 붙여 넣은 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-132">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="97d76-133">파일이 보안 Azure blob 저장소에 업로드 되 고 다음 단계를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-133">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![비 Office 365 데이터 가져오기에 대 한 파일 업로드](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![AzCopy을 사용 하 여 비 Office 365 데이터 가져오기](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="97d76-136">마지막으로 보안 & 준수로 돌아간 **다음: 프로세스 파일** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-136">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="97d76-137">이렇게 하면 업로드 된 파일의 처리, 텍스트 추출 및 인덱싱이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-137">This initiates processing, text extraction, and indexing of the uploaded files.</span></span>  <span data-ttu-id="97d76-138">여기에서 처리의 진행 상황과 **작업** 탭을 추적할 수 있습니다.  완료 되 면 새 파일을 증거 집합에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-138">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files are available in the evidence set.</span></span>  <span data-ttu-id="97d76-139">처리가 완료 되 면 마법사를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97d76-139">After processing is complete, you can dismiss the wizard.</span></span>

![Office가 아닌 365 가져오기 프로세스 파일](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

