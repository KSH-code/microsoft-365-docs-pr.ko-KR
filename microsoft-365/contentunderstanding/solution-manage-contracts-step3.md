---
title: 3단계. 이 Power Automate 사용하여 계약 처리 흐름 만들기
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/19/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 사용자 계정을 사용하여 Power Automate 솔루션을 사용하여 계약을 처리하기 위한 흐름을 만드는 Microsoft 365 알아보십시오.
ms.openlocfilehash: 54e92f36b19cefde92111cdbc960fad7715cf8b0
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583103"
---
# <a name="step-3-use-power-automate-to-create-your-flow-to-process-your-contracts"></a><span data-ttu-id="d423a-104">3단계.</span><span class="sxs-lookup"><span data-stu-id="d423a-104">Step 3.</span></span> <span data-ttu-id="d423a-105">이 Power Automate 사용하여 계약 처리 흐름 만들기</span><span class="sxs-lookup"><span data-stu-id="d423a-105">Use Power Automate to create your flow to process your contracts</span></span>

<span data-ttu-id="d423a-106">계약 관리 채널을 만들며 문서 라이브러리에 SharePoint 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-106">You've created your Contract Management channel and have attached your SharePoint document library.</span></span> <span data-ttu-id="d423a-107">다음 단계는 Syntex 모델이 식별하고 분류하는 Power Automate 처리하기 위한 SharePoint 흐름을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-107">The next step is to create a Power Automate flow to process your contracts that your SharePoint Syntex model identifies and classifies.</span></span> <span data-ttu-id="d423a-108">이 단계는 문서 라이브러리에서 Power Automate 흐름을 만들어 [SharePoint 있습니다.](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01)</span><span class="sxs-lookup"><span data-stu-id="d423a-108">You can do this step by [creating a Power Automate flow in your SharePoint document library](https://support.microsoft.com/office/create-a-flow-for-a-list-or-library-in-sharepoint-or-onedrive-a9c3e03b-0654-46af-a254-20252e580d01).</span></span>

<span data-ttu-id="d423a-109">계약 관리 솔루션의 경우 다음과 같은 작업을 Power Automate 흐름을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-109">For your contracts management solution, you want to create a Power Automate flow to do the following actions:</span></span>

-  <span data-ttu-id="d423a-110">SharePoint 모델에 의해 계약이 분류된 후 계약 상태를 검토 중으로 **변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="d423a-110">After a contract has been classified by your SharePoint Syntex model, change the contract status to **In review**.</span></span>
- <span data-ttu-id="d423a-111">그러면 계약이 검토된 후 승인되거나 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-111">The contract is then reviewed and is either approved or rejected.</span></span>
- <span data-ttu-id="d423a-112">승인된 계약의 경우 계약 정보는 결제 처리를 위해 탭에 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-112">For approved contracts, the contract information is posted to a tab for payment processing.</span></span>
- <span data-ttu-id="d423a-113">거부된 계약의 경우 팀에서 추가 분석을 위해 통보됩니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-113">For rejected contracts, the team is notified for further analysis.</span></span> 

<span data-ttu-id="d423a-114">다음 다이어그램은 계약 관리 Power Automate 대한 흐름을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="d423a-114">The following diagram shows the Power Automate flow for the contract management solution.</span></span>

![Flow 전체 솔루션을 보여 주어 다이어그램을 작성합니다.](../media/content-understanding/flow-entire-process.png)

## <a name="prepare-your-contract-for-review"></a><span data-ttu-id="d423a-116">검토를 위한 계약 준비</span><span class="sxs-lookup"><span data-stu-id="d423a-116">Prepare your contract for review</span></span>

<span data-ttu-id="d423a-117">SharePoint Syntex 문서 이해 모델에 의해 계약이 식별 및 분류되면 Power Automate 흐름은 먼저 상태를 검토 중으로 **변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="d423a-117">When a contract is identified and classified by your SharePoint Syntex document understanding model, the Power Automate flow will first change the status to **In review**.</span></span>

![업데이트 상태.](../media/content-understanding/flow-overview.png)

<span data-ttu-id="d423a-119">파일을 체크 아웃한 후 상태 값을 검토 중으로 **변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="d423a-119">After checking out the file, change the status value to **In review**.</span></span>

![검토 상태입니다.](../media/content-understanding/in-review.png)

<span data-ttu-id="d423a-121">다음 단계는 계약이 검토를 기다리고 계약 관리 채널에 게시할 수 있는 적응형 카드를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-121">The next step is to create an adaptive card stating that the contract is waiting for review and posting it to the Contract Management channel.</span></span>

![계약 검토 게시물.](../media/content-understanding/contract-approval-post.png)


![검토할 적응형 카드를 만들 수 있습니다.](../media/content-understanding/adaptive-card.png)

<span data-ttu-id="d423a-124">다음 코드는 Power Automate 흐름에서 이 단계에 사용되는 JSON입니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-124">The following code is the JSON used for this step in the Power Automate flow.</span></span>

```JSON
{
"$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
"type": "AdaptiveCard",
"version": "1.0",
"body": [
    {
    "type": "TextBlock",
    "text": "Contract approval request",
    "size": "large",
    "weight": "bolder",
     "wrap": true
    },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Date created",
                            "value": "@{triggerOutputs()?['body/Modified']} "
                        },
                        {
                            "title": "Link",
                            "value": "[@{triggerOutputs()?['body/{FilenameWithExtension}']}](@{triggerOutputs()?['body/{Link}']})"
                        }
                    ]
                }
            ]
         },
    {
    "type": "TextBlock",
    "text": "Comment:"
    },
        {
            "type": "Input.Text",
            "placeholder": "Enter comments",
            "id": "acComments"
        }
],
"actions": [
    {
    "type": "Action.Submit",
    "title": "Approve",
    "data": {
        "x": "Approve"
    }
    },
    {
    "type": "Action.Submit",
    "title": "Reject",
    "data": {
        "x": "Reject"
    }
    }
]
}
```


## <a name="conditional"></a><span data-ttu-id="d423a-125">조건부</span><span class="sxs-lookup"><span data-stu-id="d423a-125">Conditional</span></span>

<span data-ttu-id="d423a-126">흐름에서 다음으로 계약이 승인되거나 거부되는 조건을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-126">In your flow, next you need to create a condition in which your contract will be either  approved or rejected.</span></span>

![조건부.](../media/content-understanding/condition.png)

## <a name="if-the-contract-is-approved"></a><span data-ttu-id="d423a-128">계약이 승인된 경우</span><span class="sxs-lookup"><span data-stu-id="d423a-128">If the contract is approved</span></span>

<span data-ttu-id="d423a-129">계약이 승인되면 다음과 같은 상황이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-129">When a contract has been approved, the following things occur:</span></span>

- <span data-ttu-id="d423a-130">계약 **탭에서** 계약 카드의 상태가 **승인됨으로 변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="d423a-130">On the **Contracts** tab, the status in the contract card will change to **Approved**.</span></span>

   ![카드 상태가 승인되었습니다.](../media/content-understanding/approved-contracts-tab.png)

- <span data-ttu-id="d423a-132">흐름에서 상태가 **승인됨으로 변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="d423a-132">In your flow, the status is changed to **Approved**.</span></span>

   ![Flow 상태 승인됨.](../media/content-understanding/status-approved.png)

- <span data-ttu-id="d423a-134">이 솔루션에서는 지급을 관리할 수  있도록 계약 데이터가 지급용 탭에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-134">In this solution, the contract data will be added to the **For Payout** tab so that the payouts can be managed.</span></span> <span data-ttu-id="d423a-135">이 프로세스를 확장하여 흐름이 타사 금융 응용 프로그램(예: Dynamics CRM)의 결제 계약을 제출할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-135">This process can be extended to allow the flow to submit the contracts for payment by a third-party financial application (for example, Dynamics CRM).</span></span>

   ![계약이 지급으로 이동](../media/content-understanding/for-payout.png)

- <span data-ttu-id="d423a-137">흐름에서 다음 항목을 만들어 승인된 계약을 지급용 **탭으로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-137">In the flow, you create the following item to move approved contracts to the **For Payout** tab.</span></span>

   ![Flow 항목에서 결제로 이동할 수 있습니다.](../media/content-understanding/ready-for-payout.png)

- <span data-ttu-id="d423a-139">계약이 승인된 적응형 카드가 생성되고 계약 관리 채널에 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-139">An adaptive card stating that the contract has been approved is created and posted to the Contract Management channel.</span></span>

   ![계약 승인 게시.](../media/content-understanding/adaptive-card-approval.png)

   ![적응형 카드 승인.](../media/content-understanding/adaptive-card.png)


   <span data-ttu-id="d423a-142">다음 코드는 Power Automate 흐름에서 이 단계에 사용되는 JSON입니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-142">The following code is the JSON used for this step in the Power Automate flow.</span></span>

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "emphasis",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT APPROVED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Approval by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Approved date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Approval comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Ready for payout"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

## <a name="if-the-contract-is-rejected"></a><span data-ttu-id="d423a-143">계약이 거부된 경우</span><span class="sxs-lookup"><span data-stu-id="d423a-143">If the contract is rejected</span></span>

<span data-ttu-id="d423a-144">계약이 거부된 경우 다음과 같은 상황이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-144">When a contract has been rejected, the following things occur:</span></span>

- <span data-ttu-id="d423a-145">계약 **탭에서** 계약 카드의 상태가 거부 **으로 변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="d423a-145">On the **Contracts** tab, the status in the contract card will change to **Rejected**.</span></span>

   ![카드 상태가 거부됩니다.](../media/content-understanding/rejected-contracts-tab.png)

- <span data-ttu-id="d423a-147">흐름에서 계약 파일을 체크 아웃하고 상태를 거부된 것으로 변경한 다음 파일을 다시 체크 인합니다. </span><span class="sxs-lookup"><span data-stu-id="d423a-147">In your flow, you check out the contract file, change the status to **Rejected**, and then check the file back in.</span></span>

   ![Flow 상태가 거부됩니다.](../media/content-understanding/reject-flow.png)

- <span data-ttu-id="d423a-149">흐름에서 계약이 거부된 적응형 카드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-149">In your flow, you create an adaptive card stating that the contract has been rejected.</span></span>

   ![Flow 상태가 거부됩니다.](../media/content-understanding/reject-flow-item.png)

<span data-ttu-id="d423a-151">다음 코드는 Power Automate 흐름에서 이 단계에 사용되는 JSON입니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-151">The following code is the JSON used for this step in the Power Automate flow.</span></span>

```JSON
{ 
    "type": "AdaptiveCard",
    "body": [
        {
            "type": "Container",
            "style": "attention",
            "items": [
                {
                    "type": "ColumnSet",
                    "columns": [
                        {
                            "type": "Column",
                            "items": [
                                {
                                    "type": "TextBlock",
                                    "size": "Large",
                                    "weight": "Bolder",
                                    "text": "CONTRACT REJECTED"
                                }
                            ],
                            "width": "stretch"
                        }
                    ]
                }
            ],
            "bleed": true
        },
        {
            "type": "Container",
            "items": [
                {
                    "type": "FactSet",
                    "spacing": "Large",
                    "facts": [
                        {
                            "title": "Client",
                            "value": "@{triggerOutputs()?['body/Client']}"
                        },
                        {
                            "title": "Contractor",
                            "value": "@{triggerOutputs()?['body/Contractor']}"
                        },
                        {
                            "title": "Fee amount",
                            "value": "@{triggerOutputs()?['body/FeeAmount']}"
                        },
                        {
                            "title": "Rejected by",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responder']['displayName']}"
                        },
                        {
                            "title": "Rejected date",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['responseTime']}"
                        },
                        {
                            "title": "Comment",
                            "value": "@{body('Post_an_Adaptive_Card_to_a_Teams_channel_and_wait_for_a_response')?['data']['acComments']}"
                        },
                        {
                            "title": " ",
                            "value": " "
                        },
                        {
                            "title": "Status",
                            "value": "Needs review"
                        }
                    ]
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "version": "1.2",
    "fallbackText": "This card requires Adaptive Cards v1.2 support to be rendered properly."
}
```

- <span data-ttu-id="d423a-152">카드가 계약 관리 채널에 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d423a-152">The card is posted in the Contract Management channel.</span></span>

   ![Flow 적응형 카드를 거부합니다.](../media/content-understanding/rejected.png)