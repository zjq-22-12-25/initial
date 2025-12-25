graph LR
    %% 核心实体：基准测试集
    Benchmark(LLM4Mat-Bench)

    %% 实体类样式定义
    classDef dataSource fill:#e1f5fe,stroke:#01579b,stroke-width:2px;
    classDef property fill:#fff9c4,stroke:#fbc02d,stroke-width:1px;
    classDef count fill:#e0f2f1,stroke:#00695c,stroke-width:1px,stroke-dasharray: 5 5;
    classDef type fill:#f3e5f5,stroke:#7b1fa2,stroke-width:1px;
    classDef modality fill:#fbe9e7,stroke:#bf360c,stroke-width:2px;

    %% ---------------------------------------------------------
    %% 分支 1: 输入模态 (Input Modalities)
    %% Triple: (LLM4Mat-Bench, supports_modality, Modality)
    %% ---------------------------------------------------------
    Benchmark -- supports_modality --> Mod1(Composition / Chemical Formula):::modality
    Benchmark -- supports_modality --> Mod2(CIF Structure):::modality
    Benchmark -- supports_modality --> Mod3(Text Description):::modality

    %% ---------------------------------------------------------
    %% 分支 2: 数据来源 (Data Sources) & 样本量 & 属性
    %% Triple: (LLM4Mat-Bench, contains_dataset, DataSource)
    %% Triple: (DataSource, has_sample_count, Count)
    %% Triple: (DataSource, includes_property, Property)
    %% ---------------------------------------------------------

    %% 1. OQMD
    Benchmark -- contains_dataset --> DS_OQMD(OQMD):::dataSource
    DS_OQMD -- has_sample_count --> C_OQMD(964,403 Samples):::count
    DS_OQMD -- includes_property --> P_Bandgap_OQMD(Bandgap):::property
    DS_OQMD -- includes_property --> P_FEPA_OQMD(Formation Energy Per Atom):::property

    %% 2. JARVIS-QETB
    Benchmark -- contains_dataset --> DS_JQ(JARVIS-QETB):::dataSource
    DS_JQ -- has_sample_count --> C_JQ(623,989 Samples):::count
    DS_JQ -- includes_property --> P_FEPA_JQ(Formation Energy Per Atom):::property
    DS_JQ -- includes_property --> P_EPA_JQ(Energy Per Atom):::property
    DS_JQ -- includes_property --> P_TotEn_JQ(Total Energy):::property
    DS_JQ -- includes_property --> P_IndGap_JQ(Indirect Bandgap):::property

    %% 3. GNOME
    Benchmark -- contains_dataset --> DS_GNOME(GNOME):::dataSource
    DS_GNOME -- has_sample_count --> C_GNOME(376,276 Samples):::count
    DS_GNOME -- includes_property --> P_FEPA_GNOME(Formation Energy Per Atom):::property
    DS_GNOME -- includes_property --> P_Bandgap_GNOME(Bandgap):::property
    DS_GNOME -- includes_property --> P_DEPA_GNOME(Decomposition Energy Per Atom):::property
    DS_GNOME -- includes_property --> P_TotEn_GNOME(Total Energy):::property
    DS_GNOME -- includes_property --> P_Vol_GNOME(Volume):::property
    DS_GNOME -- includes_property --> P_Dens_GNOME(Density Atomic):::property

    %% 4. Materials Project (MP)
    Benchmark -- contains_dataset --> DS_MP(Materials Project):::dataSource
    DS_MP -- has_sample_count --> C_MP(146,143 Samples):::count
    DS_MP -- includes_property --> P_Bandgap_MP(Bandgap):::property
    DS_MP -- includes_property --> P_FEPA_MP(Formation Energy Per Atom):::property
    DS_MP -- includes_property --> P_EPA_MP(Energy Per Atom):::property
    DS_MP -- includes_property --> P_Ehull_MP(Energy Above Hull):::property
    DS_MP -- includes_property --> P_Efermi_MP(Fermi Energy):::property
    DS_MP -- includes_property --> P_Dens_MP(Density / Density Atomic):::property
    DS_MP -- includes_property --> P_Vol_MP(Volume):::property
    DS_MP -- includes_property --> P_Stable_MP(Is Stable):::property
    DS_MP -- includes_property --> P_GapDir_MP(Is Gap Direct):::property

    %% 5. hMOF
    Benchmark -- contains_dataset --> DS_hMOF(hMOF):::dataSource
    DS_hMOF -- has_sample_count --> C_hMOF(132,743 Samples):::count
    DS_hMOF -- includes_property --> P_LCD_hMOF(LCD / Largest Cavity Dia.):::property
    DS_hMOF -- includes_property --> P_PLD_hMOF(PLD / Pore-Limiting Dia.):::property
    DS_hMOF -- includes_property --> P_CO2_hMOF(Max/Min CO2 Adsorption):::property
    DS_hMOF -- includes_property --> P_Void_hMOF(Void Fraction):::property
    DS_hMOF -- includes_property --> P_Surf_hMOF(Surface Area):::property

    %% 6. Cantor HEA
    Benchmark -- contains_dataset --> DS_Cantor(Cantor HEA):::dataSource
    DS_Cantor -- has_sample_count --> C_Cantor(84,019 Samples):::count
    DS_Cantor -- includes_property --> P_FEPA_Cantor(Formation Energy Per Atom):::property
    DS_Cantor -- includes_property --> P_EPA_Cantor(Energy Per Atom):::property
    DS_Cantor -- includes_property --> P_Ehull_Cantor(Energy Above Hull):::property
    DS_Cantor -- includes_property --> P_VPA_Cantor(Volume Per Atom):::property

    %% 7. JARVIS-DFT
    Benchmark -- contains_dataset --> DS_JDFT(JARVIS-DFT):::dataSource
    DS_JDFT -- has_sample_count --> C_JDFT(75,965 Samples):::count
    DS_JDFT -- includes_property --> P_BandgapOPT_JDFT(Bandgap OPT/MBJ):::property
    DS_JDFT -- includes_property --> P_FEPA_JDFT(Formation Energy Per Atom):::property
    DS_JDFT -- includes_property --> P_Ehull_JDFT(Energy Above Hull):::property
    DS_JDFT -- includes_property --> P_TotEn_JDFT(Total Energy):::property
    DS_JDFT -- includes_property --> P_ExfEn_JDFT(Exfoliation Energy):::property
    DS_JDFT -- includes_property --> P_Mech_JDFT(Bulk/Shear Modulus Kv/Gv):::property
    DS_JDFT -- includes_property --> P_Elec_JDFT(SLME, Spillage, Piezo, EFG, Seebeck):::property

    %% 8. OMDB
    Benchmark -- contains_dataset --> DS_OMDB(OMDB):::dataSource
    DS_OMDB -- has_sample_count --> C_OMDB(12,122 Samples):::count
    DS_OMDB -- includes_property --> P_Bandgap_OMDB(Bandgap):::property

    %% 9. SNUMAT
    Benchmark -- contains_dataset --> DS_SNUMAT(SNUMAT):::dataSource
    DS_SNUMAT -- has_sample_count --> C_SNUMAT(10,372 Samples):::count
    DS_SNUMAT -- includes_property --> P_BandgapGGA_SNUMAT(Bandgap GGA/HSE/Optical):::property
    DS_SNUMAT -- includes_property --> P_Direct_SNUMAT(Is Direct / Is Direct HSE):::property
    DS_SNUMAT -- includes_property --> P_SOC_SNUMAT(SOC / Spin Orbit Coupling):::property

    %% 10. QMOF
    Benchmark -- contains_dataset --> DS_QMOF(QMOF):::dataSource
    DS_QMOF -- has_sample_count --> C_QMOF(7,656 Samples):::count
    DS_QMOF -- includes_property --> P_Bandgap_QMOF(Bandgap):::property
    DS_QMOF -- includes_property --> P_TotEn_QMOF(Total Energy):::property
    DS_QMOF -- includes_property --> P_LCDPLD_QMOF(LCD / PLD):::property

    %% ---------------------------------------------------------
    %% 分支 3: 任务类型 (Task Types)
    %% Triple: (Property, has_task_type, TaskType)
    %% ---------------------------------------------------------
    TaskReg(Regression Task):::type
    TaskCls(Classification Task):::type

    %% 链接分类任务
    P_Stable_MP -.-> TaskCls
    P_GapDir_MP -.-> TaskCls
    P_Direct_SNUMAT -.-> TaskCls
    P_SOC_SNUMAT -.-> TaskCls

    %% 链接回归任务 (示例性链接，避免线条过于杂乱)
    P_Bandgap_OQMD -.-> TaskReg
    P_FEPA_JQ -.-> TaskReg
    P_Bandgap_MP -.-> TaskReg
    P_LCD_hMOF -.-> TaskReg
    P_BandgapOPT_JDFT -.-> TaskReg
