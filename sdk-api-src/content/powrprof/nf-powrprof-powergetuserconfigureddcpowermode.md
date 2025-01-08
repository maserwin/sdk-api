---
UID: NF:powersetting.PowerGetUserConfiguredDCPowerMode
title: PowerGetUserConfiguredDCPowerMode function (powrprof.h)
description: Gets the user configured power mode the device uses when on AC.
helpviewer_keywords: ["GUID_PROCESSOR_SETTINGS_SUBGROUP","NO_SUBGROUP_GUID","PowerGetUserConfiguredDCPowerMode","PowerGetUserConfiguredDCPowerMode function","base.powergetuserconfigureddcpowermode","powersetting/PowerGetUserConfiguredDCPowerMode","powrprof/PowerGetUserConfiguredDCPowerMode"]
old-location:
tech.root: power
ms.assetid: 45d704f1-bde5-4622-a87c-36872a01ac90
ms.date: 07/24/2023
ms.keywords: GUID_PROCESSOR_SETTINGS_SUBGROUP, NO_SUBGROUP_GUID, PowerGetUserConfiguredDCPowerMode, PowerGetUserConfiguredDCPowerMode function, base.powergetuserconfigureddcpowermode, powersetting/PowerGetUserConfiguredDCPowerMode, powrprof/PowerGetUserConfiguredDCPowerMode
req.header: powrprof.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 11 [desktop apps only]
req.target-min-winversvr: Windows Server 23H2 [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: powrprof.lib
req.dll: powrprof.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 23H2
f1_keywords:
 - PowerGetUserConfiguredDCPowerMode
 - powrprof/PowerGetUserConfiguredDCPowerMode
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - powrprof.dll
 - api-ms-win-power-setting-l1-1-0.dll
api_name:
 - PowerGetUserConfiguredDCPowerMode
---

# PowerGetUserConfiguredDCPowerMode function

## -description

Retrieves the user configured power mode GUID for when the device is in a DC (battery/drain) supply state.

## -parameters

### -param PowerModeGuid [out]

A pointer to a GUID buffer that receives the user configured power mode GUID on a successful return.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="GUID_POWER_MODE_BEST_EFFICIENCY"></a><a id="guid_power_mode_best_efficiency"></a><dl>
<dt><b>GUID_POWER_MODE_BEST_EFFICIENCY</b></dt>
<dt>961cc777-2547-4f9d-8174-7d86181b8a7a</dt>
</dl>
</td>
<td width="60%">
This power mode indicates the device is biased towards energy efficiency.

</td>
</tr>
<tr>
<td width="40%"><a id="GUID_POWER_MODE_NONE"></a><a id="guid_power_mode_none"></a><dl>
<dt><b>GUID_POWER_MODE_NONE</b></dt>
<dt>00000000-0000-0000-0000-000000000000</dt>
</dl>
</td>
<td width="60%">
This power mode indicates the device has a balance between performance and energy efficiency.

</td>
</tr>
<tr>
<td width="40%"><a id="GUID_POWER_MODE_BEST_PERFORMANCE"></a><a id="guid_power_mode_best_performance"></a><dl>
<dt><b>GUID_POWER_MODE_BEST_PERFORMANCE</b></dt>
<dt>ded574b5-45a0-4f42-8737-46345c09c238</dt>
</dl>
</td>
<td width="60%">
This power mode indicates the device is biased towards performance.

</td>
</tr>
</table>

## -returns

If the function succeeds, it returns <b>ERROR_SUCCESS</b>. If the function fails, it returns a system error code.

## -remarks

Windows comes installed with three default power modes that have preconfigured power setting values. The power mode names “Best Power Efficiency”, “Balanced”, and “Best Performance”. These power modes cannot be removed or changed and are the only supported values for the user configured power mode as of v1 of this API.

Power modes were previously referred to as "overlays" or "overlay schemes".

## -see-also

<a href="/windows/desktop/Power/power-management-functions">Power Management Functions</a>
