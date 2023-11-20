
Now the embeddings are fused and we can start training 



# what are database specific values variables etc. 

### string values
- the path to the original images 
- the path to the embedded images 
- the path to the fused embeddings 
- the file name of the data dict 
- where the not_embedded file should be saved
### methods 
- how ids are extracted from file_name 
- how to create the data_path file 
- how to create path lists for the embedding part 
- how to fuse the embeddings 

### database relevant only 
- how to handle non embedded files 
- 
# What i will do today 
go throug the create_emb_script and ensure that
- [ ] the embeddings for UNCW are saved in : `/work3/s166154/Data/Embedding/UNCW/REC_MODEL/Album2/*`
- [ ] fused embeddings are saved in : `/work3/s166154/Data/Embedding/UNCW/REC_MODEL/fused_embeddings.txt`
- [ ] that no model specific strings are in `uncw_database`
- [ ] that no model specific strings are in `create_emb_new`
- [ ] that the not embedded file is saved in : `/work3/s166154/Data/Embedding/UNCW/REC_MODEL/not_embedded.txt`
