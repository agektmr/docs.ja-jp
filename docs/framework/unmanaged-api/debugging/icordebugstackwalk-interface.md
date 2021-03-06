---
title: ICorDebugStackWalk インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb58040394d99ae0c5a10672946fa5a6ead5e751
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54533417"
---
# <a name="icordebugstackwalk-interface"></a>ICorDebugStackWalk インターフェイス
スレッドのスタック上のマネージド メソッド (フレーム) を取得するメソッドを提供します。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[GetContext メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|現在のフレームのコンテキストを返します、`ICorDebugStackWalk`オブジェクト。|  
|[SetContext メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|セット、`ICorDebugStackWalk`オブジェクトの現在のスレッドの有効なコンテキストのコンテキスト。|  
|[Next メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|移動、`ICorDebugStackWalk`次のフレームにオブジェクト。|  
|[GetFrame メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|内の現在のフレームを取得、`ICorDebugStackWalk`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [デバッグ インターフェイス](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [デバッグ](../../../../docs/framework/unmanaged-api/debugging/index.md)
