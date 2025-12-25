graph LR
    %% 核心节点定义
    Dataset[BlendNet 数据集]
    
    %% 第一层级：主要维度
    Dimension_Category[维度 1: 物品类别]
    Dimension_Type[维度 2: 指令类型]
    Dimension_Complexity[维度 3: 复杂度/长度]
    Composition[数据构成]

    %% 关系连接：数据集 -> 维度
    Dataset -->|基于 Locarno 分类系统| Dimension_Category
    Dataset -->|基于 MBTI 人格类型| Dimension_Type
    Dataset -->|基于 单词数量| Dimension_Complexity
    Dataset -->|组成部分| Composition

    %% 维度 1: 物品类别 (Object Categories) [Source: 440-457]
    Dimension_Category --> Cat_Tech["Tech (科技设备)"]
    Dimension_Category --> Cat_Music["Music (乐器)"]
    Dimension_Category --> Cat_Animal["Animal (动物用品)"]
    Dimension_Category --> Cat_Furn["Furn (家具)"]
    Dimension_Category --> Cat_Transport["Transport (交通工具)"]
    Dimension_Category --> Cat_Office["Office (办公用品)"]
    Dimension_Category --> Cat_Food["Food (食品)"]
    Dimension_Category --> Cat_MedLab["MedLab (医疗/实验设备)"]
    Dimension_Category --> Cat_Fashion["Fashion (时尚服饰)"]
    Dimension_Category --> Cat_Graphics["Graphics (图形符号)"]
    Dimension_Category --> Cat_Recre["Recre (娱乐/体育用品)"]
    Dimension_Category --> Cat_Tools["Tools (工具硬件)"]
    Dimension_Category --> Cat_Travel["Travel (旅行用品)"]
    Dimension_Category --> Cat_Power["Power (电力系统)"]
    Dimension_Category --> Cat_Cuisine["Cuisine (烹饪机器)"]
    Dimension_Category --> Cat_Home["Home (家居用品)"]

    %% 维度 2: 指令类型 (Instruction Types) [Source: 459-475]
    Dimension_Type --> Type_Verbal["Verbal (动作/语言问答)"]
    Dimension_Type --> Type_Look["Look (外观描述)"]
    Dimension_Type --> Type_Use["Use (特定用途)"]
    Dimension_Type --> Type_Deco["Deco (装饰风格)"]
    Dimension_Type --> Type_Feel["Feel (感官/触觉)"]
    Dimension_Type --> Type_Comp["Comp (比较/历史风格)"]
    Dimension_Type --> Type_Feat["Feat (特征描述)"]
    Dimension_Type --> Type_Design["Design (创意设计)"]

    %% 维度 3: 复杂度/长度 (Instruction Length) [Source: 478-485]
    Dimension_Complexity --> Len_VS["VS (极短)"]
    Dimension_Complexity --> Len_S["S (短)"]
    Dimension_Complexity --> Len_M["M (中等)"]
    Dimension_Complexity --> Len_L["L (长)"]
    Dimension_Complexity --> Len_E["E (扩展/超长)"]

    %% 数据构成 [Source: 153]
    Composition --> Part_Human["BlendNet-Human (人工验证, 2k)"]
    Composition --> Part_GPT["BlendNet-GPT (GPT验证, 6k)"]

    %% 样式定义 (可选，用于美化)
    classDef mainNode fill:#f9f,stroke:#333,stroke-width:2px;
    classDef dimNode fill:#bbf,stroke:#333,stroke-width:1px;
    classDef leafNode fill:#efe,stroke:#333,stroke-width:1px;

    class Dataset mainNode;
    class Dimension_Category,Dimension_Type,Dimension_Complexity,Composition dimNode;
    class Cat_Tech,Cat_Music,Cat_Animal,Cat_Furn,Cat_Transport,Cat_Office,Cat_Food,Cat_MedLab,Cat_Fashion,Cat_Graphics,Cat_Recre,Cat_Tools,Cat_Travel,Cat_Power,Cat_Cuisine,Cat_Home leafNode;
    class Type_Verbal,Type_Look,Type_Use,Type_Deco,Type_Feel,Type_Comp,Type_Feat,Type_Design leafNode;
    class Len_VS,Len_S,Len_M,Len_L,Len_E leafNode;
    class Part_Human,Part_GPT leafNode;
