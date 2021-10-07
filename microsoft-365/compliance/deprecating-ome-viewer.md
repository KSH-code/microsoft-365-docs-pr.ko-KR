---
title: 메시지 암호화 뷰어 앱 사용 안
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: OME(Office 365 메시지 암호화) 뷰어 앱은 2018년 Android 및 Apple 스토어에서 제거되었습니다.
ms.openlocfilehash: 0eded17f4da5347e1f1a88031a780cee5f8b1dee
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152985"
---
# <a name="deprecating-message-encryption-viewer-app"></a>메시지 암호화 뷰어 앱 사용 안

2018년 8월 15일, Android 및 Apple 스토어에서 OME(Office 365 메시지 암호화) 뷰어 모바일 앱을 제거했습니다. Office 365 메시지 암호화 뷰어 모바일 앱은 Apple 및 Android 휴대폰에서 이전 버전의 OME로 암호화된 전자 메일 메시지 및 첨부 파일을 읽는 데 필요했습니다. OME 뷰어 앱을 제거하는 것 외에도 이전 버전의 OME는 변경하지 않습니다.
  
## <a name="changes-from-august-2018"></a>2018년 8월 변경 내용

2017년 9월에 발표된 바에 따라 사용자가 모바일 앱의 요구 사항 없이도 암호화되고 보호된 메시지를 조직 내부 [또는 외부의](https://aka.ms/ome2017) 사용자에게 보낼 수 있도록 새로운 버전의 Office 365 메시지 암호화 릴리스했습니다. 그 이후로 추가 기능이 추가되었습니다.
  
- [암호화 전용 템플릿](https://aka.ms/encryptonly)

- [첨부 파일 암호 해독 제어](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

이 변경으로 사용자는 더 이상 8월 1일 Office 365 메시지 암호화 뷰어 앱을 다운로드할 수 없습니다. 따라서 메일 받는 사람은 일부 Android 및 Apple 모바일 장치에서 이전 버전의 OME로 암호화된 메시지를 읽을 수 없습니다. 그러나 데스크톱 브라우저를 통해 개인 컴퓨터에서 이러한 메시지를 읽을 수 있습니다. 이미 앱을 다운로드한 사용자는 계속 앱을 사용할 수 있습니다.
  
## <a name="why-this-change-was-made"></a>이러한 변경이 이행된 이유

새 버전의 OME는 더 이상 모바일 앱이 보호된 전자 메일 메시지 및 첨부 파일을 읽을 필요는 없습니다. 새 OME 기능을 사용하는 고객은 모바일에서 보호된 메시지를 볼 Outlook 비 고객은 브라우저에서 보호된 메시지를 볼 수 있습니다.
  
사용자가 모바일 앱을 다운로드하도록 요구하는 것은 고객이 보호된 메시지를 볼 수 있는 또 다른 Hurdle입니다. 새로운 Office 365 메시지 암호화 기능은 더 나은 모바일 환경을 제공합니다.
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>이전 버전의 2016을 계속 사용할 수 Office 365 메시지 암호화

이전 버전의 Office 365 메시지 암호화 더는 사용되지 않을 예정입니다. 그러나 새 버전의 Office 365 메시지 암호화이 크게 향상되어 사용자가 Outlook(데스크톱, 모바일 및 웹)에서 보호된 메시지를 직접 읽을 수 있는 기능을 포함하여 모든 사용자와 디바이스에 중요한 데이터를 더 쉽게 암호화하고 보호할 수 있습니다. 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>이 변경을 준비하기 위해 해야 할 일

조직에서 현재 OME 뷰어 앱이 필요한 받는 사람에게 암호화된 첨부 파일을 전송하는 경우 설명서 및 교육 리소스를 업데이트해야 합니다.
  
조직에서 새로운 기능과 Exchange 기능을 활용할 수 있도록 현재 버전의 OME를 사용하기 위해 기존 메일 흐름 규칙을 업데이트하는 것이 좋습니다. 새 OME 기능을 설정한 후 받는 사람은 OME 뷰어 앱이 모바일 장치에서 암호화된 메시지를 읽을 필요가 없습니다.
  
조직에 적절한 새 OME 기능으로 이동하는 계획을 세우는 것이 좋습니다. 자세한 내용은 [Set up new Office 365 메시지 암호화 capabilities을 참조하십시오.](set-up-new-message-encryption-capabilities.md) 새 기능이 먼저 작동되는 방식에 대한 자세한 내용은 [Office 365 메시지 암호화.](ome.md)
  

