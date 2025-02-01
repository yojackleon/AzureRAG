# AI Home Schooling Assistant

This project builds a RAG pipeline using Azure services to query GCSE level examination board information including the curriculum and past papers. 

The purpose is to support home schooling using LLMs.

In addition, I will experiment with marking homework using Azure's AI services to scan and evaluate work on a weekly basis against a study plan based on the curriculum.

The plan is as follows: - 
1. Create a RAG of the GCSE curriculum published by a selected Exam board for one subject such as Maths.
2. Use Azure AI to create a curriculum for the 2 years of study.
3. Add past examination papers and marking schemes.
4. Test marking efficacy based on the marking schemes, this will need to scan handwritten answers. 
5. Add the following subjects: English Literature, English Language, History, Ethics, Sociology.
6. Add the ability to evaluation weekly homework based on progress against the curriculum, and provide constructive suggestions. 

# Test Queries
1. What topics do i need to learn for GCSE Higher Maths for Edexcel ?
2. Build me week by week, 2 year study plan for GCSE Higher Maths for Edexcel including mock exams at recommended intervals.
3. Which topics occur most and least frequenty in past exam papers for GCSE Higher Maths with Edexcel?
4. Which topics always appear on past exam papers for GCSE Higher Maths with Edexcel?
5. What is the statistical minimum set of topics I need to learn to pass GCSE Higher Maths for Edexcel with 60% according to past exam papers?
6. This is my homework for week 5 for  GCSE Higher Maths for Edexcel, please mark and provide feedback and learning suggestions.

# The Data

1. Store Subject specs published by exam boards in folder Subject Specs with filename
   
`<examboard>-<level>-<subject>-<year>-specification`

Where: - 
- Level is GCSE for us
- Year is the year the spec was released

We will push the files into Azure Files because we don't need to worry about massive scale for the specs. 

2. We need to chunk the specification files. Most specs are organised by Topic so we will use Topic as a first tier for chunking. 
   In addition most subjects have a foundation and a higher level, this should be the second level of tiering the chunks if possible. Although seperation of levels in the spec is not always delineated clearly.
   Most specs also contain a lot of other information, which is not useful at this stage so will be discarded. 
3. Enrich chunks with meta data such as 
   1. Top level topic
   2. Sub topic
   3. Requirement level ( foundation or higher ) 
   4. Year of spec
   5. Exam board
   6. Subject
   7. Qualification level ( eg GCSE, ALevel, other ) 
4. Consider augmenting chucks to aid search, for example with synonyms.
5. Vectorise chunks using technology to be determined.
6. Create search index, most likely for Azure AI Search

# Considerations

1. How will we evaluate the effectiveness of each stage of implementation ?
   