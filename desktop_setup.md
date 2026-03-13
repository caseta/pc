# Desktop Setup Diagram

This is an updated Mermaid version based on your color-coded reference image.

Color mapping used from your markup:
- `Red` = Gaming PC
- `Yellow` = Switch
- `Green` = Right monitor
- `Blue` = Center monitor
- `Purple` = Left monitor

> Note: Port groups are now modeled exactly by device color box. Cable paths are drawn for the visible runs; if you want, I can do one more pass to label each cable with a nickname (e.g., `Cable A`, `Cable B`) for easier future edits.

```mermaid
flowchart TB
    %% Devices and exact port sets from your color boxes
    subgraph LEFT["Left Monitor (Purple)"]
      LM[Left Monitor]
      LM_DP([DP])
      LM_H1([HDMI])
      LM_H2([HDMI])
      LM --- LM_DP
      LM --- LM_H1
      LM --- LM_H2
    end

    subgraph CENTER["Center Monitor (Blue)"]
      CM[Center Monitor]
      CM_DP([DP])
      CM_H1([HDMI])
      CM_H2([HDMI])
      CM --- CM_DP
      CM --- CM_H1
      CM --- CM_H2
    end

    subgraph RIGHT["Right Monitor (Green)"]
      RM[Right Monitor]
      RM_H1([HDMI])
      RM_H2([HDMI])
      RM_DP([DP])
      RM --- RM_H1
      RM --- RM_H2
      RM --- RM_DP
    end

    subgraph SWITCH["Switch (Yellow)"]
      SW[Switch]
      SW_DP1([DP])
      SW_DP2([DP])
      SW_H1([HDMI])
      SW_EXT_H([HDMI external])
      SW --- SW_DP1
      SW --- SW_DP2
      SW --- SW_H1
    end

    subgraph PCBOX["Gaming PC (Red)"]
      PC[Gaming PC]
      PC_DP1([DP])
      PC_H1([HDMI])
      PC_DP2([DP])
      PC_DP3([DP])
      PC --- PC_DP1
      PC --- PC_H1
      PC --- PC_DP2
      PC --- PC_DP3
    end

    %% Layout control:
    %% - top row ordered left -> center -> right -> switch
    %% - gaming PC below center/right area
    subgraph TOP_ROW[" "]
      direction LR
      LEFT
      CENTER
      RIGHT
      SWITCH
    end

    subgraph BOTTOM_ROW[" "]
      direction LR
      PCBOX
    end

    CENTER -.-> PCBOX

    %% Visible cable runs from the drawing
    PC_DP1 --> LM_H2
    PC_H1 --> CM_DP
    PC_DP2 --> RM_DP
    PC_DP3 --> RM_H2
    CM_H2 --> SW_DP1
    SW_DP2 --> RM_H1
    SW_H1 --> SW_EXT_H
```

## How To Update

- Open this file and edit labels/links in the Mermaid block.
- Preview in GitHub or any Mermaid-enabled Markdown viewer.
- If you want full precision, send cable mapping in this format and I will update in one pass:
  - `source port -> destination port`
  - Example: `PC_DP2 -> RightMonitor_DP`
