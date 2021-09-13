---
title: 기본 DLP 정책을 사용하여 시작
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 보고서를 사용하여 조직의 기본 DLP(데이터 손실 방지) 정책을 구체화하는 방법을 학습합니다.
ms.openlocfilehash: 95c4ebae431bea1db033826459ca1595614ab5cb
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191432"
---
# <a name="get-started-with-the-default-dlp-policy"></a>기본 DLP 정책을 사용하여 시작

첫 번째 DLP(데이터 손실 방지) 정책을 만들기 전에 DLP는 기본 정책으로 중요한 정보를 보호하는 데 도움이 됩니다. 이 기본 정책 및 권장 정책(아래 그림 참조)은 신용 카드 번호가 포함된 전자 메일 또는 문서가 조직 외부의 사용자와 공유될 때 알려 중요한 콘텐츠를 안전하게 유지하는 데 도움이 됩니다. 이 권장 내용은 보안 및  준수 센터의 홈 &amp; 페이지에서 볼 수 있습니다. 
  
이 위젯을 사용하여 공유된 중요한 정보의 수와 정보를 빠르게 확인한 다음 한 두 번의 클릭 또는 두 번으로 기본 DLP 정책을 구체화할 수 있습니다. 기본 DLP 정책은 사용자 지정이 완전히 가능하기 때문에 원하는 경우 편집할 수도 있습니다. 처음에 추천이 없는 경우 권장 섹션 아래쪽에서 **+More를** **클릭해 봐야** 합니다. 
  
![Widget named Further protect shared content.](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>보고서를 보고 기본 DLP 정책 구체화

위젯에서 사용자가 조직 외부의 사용자와 중요한 정보를 공유했다는 것을 보여 주면 아래쪽의 **DLP** 정책 구체화 를 선택하세요. 
  
자세한 보고서는 지난 30일 동안 신용 카드 번호를 포함하는 콘텐츠가 공유된 경우와 양을 보여줍니다. 규칙 일치는 위젯에 표시하는 데 최대 48시간이 걸릴 수 있습니다.
  
중요한 정보를 보호하기 위해 기본 DLP 정책은 다음을 처리합니다.
  
- 하나 이상의 신용 카드 번호를 포함하는 Exchange, SharePoint 및 OneDrive 콘텐츠가 조직 외부의 사용자와 공유되는 경우를 검색합니다.
    
- 사용자가 이 중요한 정보를 조직 외부의 사용자와 공유하려고 할 때 정책 팁을 표시하고 사용자에게 전자 메일 알림을 전송합니다. 이러한 옵션에 대한 자세한 내용은 전자 메일 알림 보내기 및 DLP 정책에 대한 정책 [팁 표시를 참조하세요.](use-notifications-and-policy-tips.md)
    
- 조직 외부의 사용자와 콘텐츠를 공유한 사람 및 콘텐츠를 공유한 경우를 추적할 수 있도록 자세한 활동 보고서를 생성합니다. [DLP](view-the-dlp-reports.md) 보고서 및 감사 [](search-the-audit-log-in-security-and-compliance.md) 로그 데이터(여기서 **활동**  =  **DLP)를** 사용하여 이 정보를 볼 수 있습니다.
    
기본 DLP 정책을 빠르게 구체화하기 위해 다음을 하게 선택할 수 있습니다.
  
- 사용자가 이 중요한 정보를 조직 외부의 사용자와 공유할 때 문제 보고서 전자 메일을 전송합니다.
    
- 전자 메일 문제 보고서에 다른 사용자를 추가합니다.
    
- 중요한 정보가 포함된 콘텐츠에 대한 액세스를 차단하지만, 사용자가 필요한 경우 사용자가 다시 설정하고 공유하거나 보낼 수 있도록 허용합니다.
    
인시던트 보고서 또는 액세스 제한에 대한 자세한 내용은 데이터 손실 방지 [참조를 참조하세요.](data-loss-prevention-policies.md)
  
나중에 이러한 옵션을 변경하려는 경우 기본 DLP 정책을 편집할 수 있습니다. 다음 섹션을 참조하세요.
  
![설정 보호라는 위젯을 사용할 수 있습니다.](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>기본 DLP 정책 편집

이 정책의 이름은 **기본 DLP 정책으로,** 보안  및 준수 센터의 정책 페이지에서 데이터 손실 방지 아래에  &amp; 표시됩니다. 
  
이 정책은 처음부터 직접 만든 DLP 정책과 동일하게 완전히 사용자 지정 가능합니다. 사용자가 더 이상 정책 팁 또는 전자 메일 알림을 받지 못하게 정책을 끄거나 삭제할 수도 있습니다.
  
![기본 DLP 정책이라는 DLP 정책](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>위젯이 나타나고 나타나지 않는 경우

보안 및 준수 **센터** 홈 페이지의  권장 섹션에  공유 콘텐츠 추가 보호라는 &amp; 위젯이 표시됩니다. 
  
이 위젯은
  
- 보안 및 준수 센터 또는 관리 센터에는 데이터 &amp; 손실 Exchange 없습니다. 이 위젯은 DLP를 시작하는 데 도움을 주기 위해 고안된 것으로, 이미 DLP 정책이 있는 경우 나타나지 않습니다.
    
- 지난 30일 동안 하나 이상의 신용 카드를 포함하는 콘텐츠가 조직 외부의 사용자와 공유된 경우
    
위젯에서 규칙 일치를 사용할 수 있는 데 최대 48시간이 걸릴 수 있으므로 외부에서 공유되는 중요한 정보가 감지된 후 권장 사항 표시에 최대 2일이 걸릴 수 있습니다.
  
마지막으로 위젯을 사용하여 기본 DLP 정책을 구체화하면 홈 페이지에서  위젯이 사라집니다. 
  

