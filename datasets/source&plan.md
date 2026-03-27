preprocessed_content.csv:"https://www.kaggle.com/datasets/jaidityachopra/esg-sustainability-reports-of-s-and-p-500-companies"

World_Bank_ESG_WIDEF.csv:"https://data360.worldbank.org/en/dataset/WB_ESG"

kaggle-esg.csv:"https://www.kaggle.com/datasets/alistairking/public-company-esg-ratings-dataset?resource=download"

esgdata.csv:"https://github.com/LCYgogogo/ESG-dataset/tree/main"

Dow30-DATASET-Q2_2024.csv: "https://www.kaggle.com/datasets/jenniferaduffy/esg-ratings-and-stock-data-for-dow-30-companies?utm_source=chatgpt.com&select=Dow30-DATASET-Q2_2024.csv"

esg_sasb_data.csv:"https://www.kaggle.com/datasets/edwardjunprung/sasb-aligned-esg-sentences"

esg_documents_for_dax_companies.csv     sdg_descriptions_with_targetsText.csv:"https://www.kaggle.com/datasets/equintel/dax-esg-media-dataset"

esgseries/* :https://www.kaggle.com/datasets/tunguz/environment-social-and-governance-data



## The 6 Objectives

- **Objective 1**: Keyword / issue extraction
- **Objective 2**: Topic classification
- **Objective 3**: Sentiment / controversy analysis
- **Objective 4**: Advanced ESG text/data analysis
- **Objective 5**: ESG score prediction
- **Objective 6**: Dashboard + recommendation/chatbot integration

## Dataset Summary

### esgdata.csv (Sheet1)

- **Parameters**: sentences, label, quality
- **Example**: sentences=我们积极履行社会责任; label=无关文本; quality=无关文本
- **Suitable objectives**: Obj1 Keyword Extraction (limited), Obj2 Topic Classification, Obj3 Sentiment/Polarity (only if labels are extended), Obj4 Advanced Text Analysis. Not suitable alone for Obj5 ESG Score Prediction or Obj6 Dashboard/Recommendation.
- **Note**: Sentence-level Chinese ESG text; current visible labels are not directly aligned to E/S/G.

### esg_documents_for_dax_companies.csv (schema provided)

- **Parameters**: company, content, datatype, date, domain, esg_topics, internal, symbol, title, url
- **Example**: company=Beiersdorf AG; datatype=report; date=2021; domain=beiersdorf.com; esg_topics=climate; social impact; symbol=BEI
- **Suitable objectives**: 12346, Can support 5 only after merging with company-year ESG scores.
- **Note**: Document-level / article-level raw text for DAX companies.

### preprocessed_content.csv (schema provided)

- **Parameters**: filename, ticker, year, preprocessed_content, ner_entities, e_score, s_score, g_score, total_score
- **Example**: filename=company_2023_report.pdf; ticker=AAPL; year=2023; preprocessed_content=cleaned annual report text ...; e_score=82.1; s_score=74.3; g_score=79.0; total_score=78.4
- **Suitable objectives**: 123456
- **Note**: This is the strongest company-year bridge dataset because text and ESG scores are already aligned.

### kaggle-esg.csv

- **Parameters**: ticker, name, currency, exchange, industry, logo, weburl, environment_grade, environment_level, social_grade, social_level, governance_grade, governance_level, environment_score, social_score, governance_score, total_score, last_processing_date, total_grade, total_level, cik
- **Example**: ticker=dis; name=Walt Disney Co; currency=USD; exchange=NEW YORK STOCK EXCHANGE, INC.; industry=Media; logo=https://static.finnhub.io/logo/ef50b4a2b263c847211b567a01edb702cae8b9ef46ca1f685...; weburl=https://thewaltdisneycompany.com/; environment_grade=A
- **Suitable objectives**: Obj4 Advanced Analysis, Obj5 ESG Score Prediction baseline, Obj6 Dashboard/Benchmarking. Not suitable alone for Obj1-3 because it has no report text.
- **Note**: Company-level ESG ratings table.

### Dow30-DATASET-Q2_2024.csv

- **Parameters**: Unique_id, Symbol, Company_name, GIC_sector, GIC_industry_group, GIC_Industry, GIC_Subindustry, Address, ESG_pulse, ESG_beta, SNP, SNP-environmental, SNP-environmental industry mean, SNP-social, SNP-social industry mean, ...
- **Example**: Unique_id=190179; Symbol=MMM; Company_name=3M Company; GIC_sector=Industrials; GIC_industry_group=Capital Goods_2010; GIC_Industry=Industrial_Conglomerates_201050; GIC_Subindustry=Industrial Conglomerates; Address=3M Center, St. Paul, MN, United States, 55144
- **Suitable objectives**: Obj4 Advanced Analysis, Obj5 ESG Score Prediction / benchmarking, Obj6 Dashboard/Recommendation. 
- **Note**: Small company-level benchmark dataset with ESG + financial variables.

### esg_sasb_data.csv

- **Parameters**: Text, Parent Label, Child Label
- **Example**: Text=AB also recognizes the importance of carving and strengthening pathways for dive...; Parent Label=Human Capital; Child Label=Employee Engagement Diversity & Inclusion
- **Suitable objectives**: 124, Limited support for 6 as a label resource.
- **Note**: Sentence-level ESG taxonomy data with parent/child topic labels.

### World_Bank_ESG_WIDEF.csv / ESGData.csv / ESGSeries*.csv / ESGCountry*.csv / ESGFootNote.csv

- **Parameters**: country/country code, indicator/series code, metadata, year columns or year field, values, definitions/notes
- **Example**: REF_AREA_LABEL=Afghanistan; INDICATOR_LABEL=Agricultural land (% of land area); 2020=...
- **Suitable objectives**: 46
- **Note**: Country-level indicator system, not company-level report data.

### sdg_descriptions_with_targetsText.csv

- **Parameters**: id, name, description, targets, targets_json_array, progress
- **Example**: id=1; name=No Poverty; description=End poverty in all its forms everywhere; targets=['1.1', 'By 2030, eradicate extreme poverty for all people everywhere, currently...; targets_json_array=[{"target":"1.1","description":"By 2030, eradicate extreme poverty for all peopl...; progress=['The impact of the COVID-19 pandemic reversed the steady progress of poverty re...
- **Suitable objectives**: 1246
- **Note**: SDG ontology / goal descriptions, useful as an auxiliary knowledge base.