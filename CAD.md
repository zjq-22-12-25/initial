```mermaid
graph LR
    %% 核心节点：BlendNet 数据集
    Dataset[("BlendNet 数据集")]

    %% 维度 1: 物品类别 (基于 Locarno 分类系统)
    Dataset -->|维度1: 物品类别| Class_Locarno["16种物品类别"]
    Class_Locarno -->|包含| Cat1["Tech (科技设备)"]
    Class_Locarno -->|包含| Cat2["Music (乐器)"]
    Class_Locarno -->|包含| Cat3["Animal (动物用品)"]
    Class_Locarno -->|包含| Cat4["Furn (家具)"]
    Class_Locarno -->|包含| Cat5["Transport (交通工具)"]
    Class_Locarno -->|包含| Cat6["Office (办公用品)"]
    Class_Locarno -->|包含| Cat7["Food (食品)"]
    Class_Locarno -->|包含| Cat8["MedLab (医疗实验)"]
    Class_Locarno -->|包含| Cat9["Fashion (时尚服饰)"]
    Class_Locarno -->|包含| Cat10["Graphics (图形符号)"]
    Class_Locarno -->|包含| Cat11["Recre (娱乐体育)"]
    Class_Locarno -->|包含| Cat12["Tools (工具硬件)"]
    Class_Locarno -->|包含| Cat13["Travel (旅行用品)"]
    Class_Locarno -->|包含| Cat14["Power (电力系统)"]
    Class_Locarno -->|包含| Cat15["Cuisine (烹饪机器)"]
    Class_Locarno -->|包含| Cat16["Home (家居用品)"]

    %% 维度 2: 指令类型 (基于 MBTI)
    Dataset -->|维度2: 指令类型| Class_MBTI["8种指令语气"]
    Class_MBTI -->|包含| Type1["Verbal (动作问答)"]
    Class_MBTI -->|包含| Type2["Look (外观描述)"]
    Class_MBTI -->|包含| Type3["Use (特定用途)"]
    Class_MBTI -->|包含| Type4["Deco (装饰风格)"]
    Class_MBTI -->|包含| Type5["Feel (感官体验)"]
    Class_MBTI -->|包含| Type6["Comp (比较/历史)"]
    Class_MBTI -->|包含| Type7["Feat (特征聚焦)"]
    Class_MBTI -->|包含| Type8["Design (创意设计)"]

    %% 维度 3: 复杂度 (基于单词数量)
    Dataset -->|维度3: 复杂度| Class_Complexity["5个长度等级"]
    Class_Complexity -->|包含| Len1["VS (极短)"]
    Class_Complexity -->|包含| Len2["S (短)"]
    Class_Complexity -->|包含| Len3["M (中等)"]
    Class_Complexity -->|包含| Len4["L (长)"]
    Class_Complexity -->|包含| Len5["E (扩展/超长)"]

    %% 数据集构成
    Dataset -->|数据构成| Composition["数据来源"]
    Composition -->|人工验证| Part1["BlendNet-Human (2k)"]
    Composition -->|GPT验证| Part2["BlendNet-GPT (6k)"]

    %% 引用来源说明
    [cite_start]%% 类别参考: [cite: 95, 440-457]
    [cite_start]%% 类型参考: [cite: 96, 458-475]
    [cite_start]%% 长度参考: [cite: 97, 476-485]
    [cite_start]%% 构成参考: [cite: 153]
```
