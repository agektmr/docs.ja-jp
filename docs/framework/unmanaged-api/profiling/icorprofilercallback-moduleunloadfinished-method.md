---
title: ICorProfilerCallback::ModuleUnloadFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7759b0815946301932ca60edaf731313d04a245
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743466"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a>ICorProfilerCallback::ModuleUnloadFinished メソッド
モジュールのアンロードが完了したことをプロファイラーに通知します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `moduleId`  
 [in]アンロードされたモジュールの ID。  
  
 `hrStatus`  
 [in]かどうか、モジュールがアンロードされた正常を示す HRESULT。  
  
## <a name="remarks"></a>Remarks  
 値`moduleId`は後の情報の要求は無効です、 [icorprofilercallback::moduleunloadstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)メソッドを返します。  
  
 クラスのアンロードの一部が後に続ける可能性があります、`ModuleUnloadFinished`コールバック。 エラーの HRESULT で`hrStatus`失敗を示します。 ただし、成功 HRESULT で`hrStatus`のみに、モジュールのアンロードの最初の部分が成功したことを示します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICorProfilerCallback インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
