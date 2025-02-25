### Run a local rag pipeline from scratch

Rundown of the steps:

1. Take text from the pdf, use it
2. Use sentencizer to find all sentences in a page and put in array
3. Split the sentence into chunks of max 10 sentences each.
4. Now split every chunk into its own object
5. Remove chunks with low token count
6. Embed the chunks in an array
7. Convert to np.array
8. Convert to torch.tensor and set device to cuda
9. Load an LLM
10. RAG creation - convert query to embedding
11. RAG creation - get top scores through dot product topk
12. RAG creation - Get the context text from chunks using the indices
13. RAG creation - fuse the context items and uery  to create an accurate prompt
14. Generate the output through tokenizer, and then decode
