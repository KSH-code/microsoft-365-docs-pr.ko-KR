---
title: 민감도 레이블을 사용하여 인시던트 대응 우선 순위 지정
description: 민감도 레이블을 사용하여 인시던트의 우선 순위를 지정하고 조사하는 방법에 대해 자세히 알아보기
keywords: 정보, 보호, 데이터, 손실, 방지,레이블, dlp, 인시던트, 조사, 조사
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d0c27ab2c6af8706e5e06a3c87b44e49c9185766
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073852"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a><span data-ttu-id="8c2b7-104">민감도 레이블을 사용하여 인시던트 대응 우선 순위 지정</span><span class="sxs-lookup"><span data-stu-id="8c2b7-104">Use sensitivity labels to prioritize incident response</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8c2b7-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8c2b7-105">**Applies to:**</span></span>
- [<span data-ttu-id="8c2b7-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8c2b7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="8c2b7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c2b7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8c2b7-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="8c2b7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8c2b7-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="8c2b7-110">일반적인 고급 영구 위협 수명 주기에는 데이터 유출이 수반됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-110">A typical advanced persistent threat lifecycle involves data exfiltration.</span></span> <span data-ttu-id="8c2b7-111">보안 인시던트에서 중요한 파일이 위험할 수 있는 조사의 우선 순위를 지정하여 회사 데이터 및 정보가 보호되는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-111">In a security incident, it's important to have the ability to prioritize investigations where sensitive files may be jeopardy so that corporate data and information are protected.</span></span>

<span data-ttu-id="8c2b7-112">Endpoint용 Defender는 민감도 레이블을 사용하여 보안 인시던트의 우선 순위를 훨씬 더 간단하게 만드는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-112">Defender for Endpoint helps to make the prioritization of security incidents much simpler with the use of sensitivity labels.</span></span> <span data-ttu-id="8c2b7-113">민감도 레이블은 기밀 정보와 같은 중요한 정보가 있는 장치를 수반할 수 있는 인시던트를 빠르게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-113">Sensitivity labels quickly identify incidents that may involve devices with sensitive information such as confidential information.</span></span> 

## <a name="investigate-incidents-that-involve-sensitive-data"></a><span data-ttu-id="8c2b7-114">중요한 데이터가 관련된 인시던트 조사</span><span class="sxs-lookup"><span data-stu-id="8c2b7-114">Investigate incidents that involve sensitive data</span></span>
<span data-ttu-id="8c2b7-115">데이터 민감도 레이블을 사용하여 인시던트 조사의 우선 순위를 지정하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-115">Learn how to use data sensitivity labels to prioritize incident investigation.</span></span>

>[!NOTE]
><span data-ttu-id="8c2b7-116">Windows 10 버전 1809 이상에서 레이블이 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-116">Labels are detected for Windows 10, version 1809 or later.</span></span>

1. <span data-ttu-id="8c2b7-117">Microsoft Defender 보안 센터에서 인시던트 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8c2b7-117">In Microsoft Defender Security Center, select **Incidents**.</span></span> 

2. <span data-ttu-id="8c2b7-118">오른쪽으로 스크롤하여 데이터 **민감도 열을** 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-118">Scroll to the right to see the **Data sensitivity** column.</span></span> <span data-ttu-id="8c2b7-119">이 열은 인시던트와 관련된 장치에서 관찰된 민감도 레이블을 반영하여 중요한 파일이 인시던트의 영향을 을 수 있는지 여부를 나타 습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-119">This column reflects sensitivity labels that have been observed on devices related to the incidents providing an indication of whether sensitive files may be impacted by the incident.</span></span>

    ![데이터 민감도 열의 이미지](images/data-sensitivity-column.png)

    <span data-ttu-id="8c2b7-121">데이터 민감도에 따라 **필터링할 수도 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="8c2b7-121">You can also filter based on **Data sensitivity**</span></span> 

    ![데이터 민감도 필터의 이미지](images/data-sensitivity-filter.png)

3. <span data-ttu-id="8c2b7-123">인시던트 페이지를 열고 추가 조사를 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-123">Open the incident page to further investigate.</span></span>

    ![인시던트 페이지 세부 정보의 이미지](images/incident-page.png)

4. <span data-ttu-id="8c2b7-125">장치 **탭을** 선택하여 민감도 레이블이 있는 파일을 저장하는 장치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-125">Select the **Devices** tab to identify devices storing files with sensitivity labels.</span></span>

    ![장치 탭의 이미지](images/investigate-devices-tab.png)
   

5. <span data-ttu-id="8c2b7-127">중요한 데이터를 저장하고 타임라인을 통해 검색하는 장치를 선택하여 영향을 줄 수 있는 파일을 식별한 다음 적절한 조치를 취하여 데이터가 보호되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-127">Select the devices that store sensitive data and search through the timeline to identify which files may be impacted then take appropriate action to ensure that data is protected.</span></span> 

   <span data-ttu-id="8c2b7-128">데이터 민감도 레이블을 검색하여 디바이스 타임라인에 표시되는 이벤트를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-128">You can narrow down the events shown on the device timeline by searching for data sensitivity labels.</span></span> <span data-ttu-id="8c2b7-129">이렇게 하면 해당 레이블 이름이 있는 파일과 관련된 이벤트만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-129">Doing this will show only events associated with files that have said label name.</span></span>

    ![레이블을 기반으로 검색 결과가 좁혀진 장치 타임라인 이미지](images/machine-timeline-labels.png)


>[!TIP]
><span data-ttu-id="8c2b7-131">이러한 데이터 포인트는 고급 헌팅에서 'DeviceFileEvents'를 통해 노출되므로 고급 쿼리 및 예약 검색에서 민감도 레이블 및 파일 보호 상태를 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c2b7-131">These data points are also exposed through the ‘DeviceFileEvents’ in advanced hunting, allowing advanced queries and schedule detection to take into account sensitivity labels and file protection status.</span></span> 
