graph TD
    %% 核心节点定义
    Dataset[航空制造评估数据集]
    Source[知识来源]
    GenMethod[生成方法]
    Q_Struct[问题结构]
    
    %% 一级分类节点
    Cat_Assembly[航空装配 Aerospace Assembly]
    Cat_Materials[航空材料 Aerospace Materials]
    Cat_Steel[结构钢 Structural Steel]

    %% 详细子类/内容节点
    Content_Assembly[飞机装配程序]
    Sub_Coatings[涂层 Coatings]
    Sub_Plating[电镀 Plating]
    Sub_Textiles[纺织品 Textiles]
    Sub_Ti[钛合金 Titanium Alloys]
    Sub_Fuels[燃料 Fuels]
    Sub_Lube[润滑油 Lubricants]
    Content_Steel[结构钢合金]

    %% 属性节点
    Textbooks[专业教科书]
    Guidelines[行业指南]
    Model_Gen[Gemini Pro Vision API]
    Review[专家审查]
    Count[约7500道题]
    Type[多项选择题(多选)]
    Options[6个选项 (A-F)]
    Diff[难易度 (易/中/难)]

    %% --- 三元组关系 (Subject -- Predicate --> Object) ---
    
    %% 数据集基本属性
    Dataset -- 包含 (contains) --> Count
    Dataset -- 来源 (derived_from) --> Source
    Dataset -- 生成于 (generated_by) --> GenMethod
    Dataset -- 组成 (consists_of) --> Q_Struct

    %% 知识来源细分
    Source -- 包括 (includes) --> Textbooks
    Source -- 包括 (includes) --> Guidelines

    %% 生成流程
    GenMethod -- 驱动模型 (driven_by) --> Model_Gen
    GenMethod -- 验证 (validated_by) --> Review

    %% 问题结构细分
    Q_Struct -- 类型 (has_type) --> Type
    Q_Struct -- 选项数 (has_options) --> Options
    Q_Struct -- 难度分级 (has_difficulty) --> Diff

    %% 数据集分类体系
    Dataset -- 分类 1 (category_1) --> Cat_Assembly
    Dataset -- 分类 2 (category_2) --> Cat_Materials
    Dataset -- 分类 3 (category_3) --> Cat_Steel

    %% 航空装配详情
    Cat_Assembly -- 关注 (focuses_on) --> Content_Assembly
    
    %% 航空材料详情 (基于 Table III 和 Section IV.B)
    Cat_Materials -- 包括 (includes) --> Sub_Coatings
    Cat_Materials -- 包括 (includes) --> Sub_Plating
    Cat_Materials -- 包括 (includes) --> Sub_Textiles
    Cat_Materials -- 包括 (includes) --> Sub_Ti
    Cat_Materials -- 包括 (includes) --> Sub_Fuels
    Cat_Materials -- 包括 (includes) --> Sub_Lube

    %% 结构钢详情
    Cat_Steel -- 关注 (focuses_on) --> Content_Steel

    %% 样式定义
    classDef main fill:#f9f,stroke:#333,stroke-width:2px;
    classDef category fill:#bbf,stroke:#333,stroke-width:2px;
    classDef subitem fill:#dfd,stroke:#333,stroke-width:1px;
    classDef attr fill:#eee,stroke:#333,stroke-dasharray: 5 5;

    class Dataset main;
    class Cat_Assembly,Cat_Materials,Cat_Steel category;
    class Content_Assembly,Sub_Coatings,Sub_Plating,Sub_Textiles,Sub_Ti,Sub_Fuels,Sub_Lube,Content_Steel subitem;
    class Source,GenMethod,Q_Struct,Textbooks,Guidelines,Model_Gen,Review,Count,Type,Options,Diff attr;
