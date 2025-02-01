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

# The Data

1. Store Subject specs published by exam boards in folder Subject Specs with filename
   
`<examboard>-<level>-<subject>-<year>-specification`

Where: - 
- Level is GCSE for us
- Year is the year the spec was released

