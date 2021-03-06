---
title: <message> このエラーは、ファイル参照と '<assemblyname>' へのプロジェクト参照との混合によって生じた可能性があります
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: f28327b4df5b15f368f736e7402179227035a06e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272553"
---
# <a name="message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a>\<メッセージ > このエラーがファイル参照とアセンブリへの参照をプロジェクトの混合によって生じた可能性があります '\<assemblyname >'
\<メッセージ > このエラーがファイル参照とアセンブリへの参照をプロジェクトの混合によって生じた可能性があります '\<assemblyname >。 この場合、ファイル参照を置き換えてお試しください '\<assemblyfilename >' プロジェクトで'\<projectname1 >' への参照をプロジェクトに '\<projectname2 >'。  
  
 プロジェクト内のコードが別のプロジェクトのメンバーにアクセスしますが、ソリューションの設定では、参照を解決するのには、Visual Basic コンパイラは許可されていません。  
  
 別のアセンブリで定義された型にアクセスするには、そのアセンブリへの参照が、Visual Basic コンパイラに必要です。 これは、プロジェクト間の循環参照にならない、単一であいまいさのない参照である必要があります。  
  
 **エラー ID:** BC30971  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  どのプロジェクトが、プロジェクトからの参照に最適なアセンブリを作成しているか特定します。 この判断には、ファイル アクセスの容易さや更新の頻度などの基準を使用できます。  
  
2.  プロジェクトのプロパティに、使用する型が定義されているアセンブリを含むプロジェクトへの参照を追加します。  
  
## <a name="see-also"></a>関連項目
- [プロジェクト内の参照の管理](/visualstudio/ide/managing-references-in-a-project)
- [宣言された要素の参照](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [プロジェクトおよびソリューションのプロパティの管理](/visualstudio/ide/managing-project-and-solution-properties)
- [壊れた参照のトラブルシューティング](/visualstudio/ide/troubleshooting-broken-references)
