# Desktop Setup Diagram

This is a clean, editable Mermaid version of the hand-drawn diagram.

> Note: A few line endpoints in the photo are ambiguous, so those are marked as `unlabeled` placeholders for easy updates.

```mermaid
flowchart LR
    %% Devices
    LM[Left Monitor]
    CM[Center Monitor]
    RM[Right Monitor]
    SW[Switch]
    PC[Gaming PC]

    %% Port groups (kept separate so cable labels stay editable)
    subgraph LeftSources[Left-side cable group]
      LS_DP([DP])
      LS_H1([HDMI])
      LS_H2([HDMI])
    end

    subgraph RightSources[Right-side cable group]
      RS_DP1([DP])
      RS_DP2([DP])
      RS_H1([HDMI])
      RS_H2([HDMI])
    end

    %% Monitor input labels (from sketch)
    LM_IN_DP([DP in])
    LM_IN_H([HDMI in])

    CM_IN_DP([DP in])
    CM_IN_H1([HDMI in])
    CM_IN_H2([HDMI in])

    RM_IN_DP([DP in])
    RM_IN_H1([HDMI in])
    RM_IN_H2([HDMI in])

    %% PC output labels (from sketch)
    PC_OUT_DP1([DP out])
    PC_OUT_DP2([DP out])
    PC_OUT_DP3([DP out])
    PC_OUT_H([HDMI out])

    %% Switch-side labels (from sketch)
    SW_DP([DP])
    SW_H([HDMI])

    %% Cable runs interpreted from the sketch
    LS_DP --> LM_IN_DP
    LS_H1 --> LM_IN_H
    LS_H2 --> LM_IN_H

    LM_IN_DP --- LM
    LM_IN_H --- LM

    CM_IN_DP --- CM
    CM_IN_H1 --- CM
    CM_IN_H2 --- CM

    RM_IN_DP --- RM
    RM_IN_H1 --- RM
    RM_IN_H2 --- RM

    SW --- SW_DP
    SW --- SW_H
    SW_DP --> RM_IN_DP
    SW_H --> RM_IN_H1

    RS_DP1 --> SW_DP
    RS_DP2 --> SW_DP
    RS_H1 --> SW_H
    RS_H2 --> SW_H

    PC --- PC_OUT_DP1
    PC --- PC_OUT_DP2
    PC --- PC_OUT_DP3
    PC --- PC_OUT_H

    PC_OUT_DP1 --> CM_IN_DP
    PC_OUT_H --> CM_IN_H1
    PC_OUT_DP2 --> RM_IN_DP
    PC_OUT_DP3 --> RM_IN_H2
```

## How To Update

- Open this file and edit labels/links in the Mermaid block.
- Preview in GitHub or any Mermaid-enabled Markdown viewer.
- If you want, I can do a second pass and make it exact by walking each cable one by one with you.
