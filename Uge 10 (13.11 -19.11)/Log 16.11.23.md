---
cssclasses:
  - error-code
---


# Start:
 
The error message from yesterday is 
```err
Traceback (most recent call last):
  File "/zhome/6c/3/121122/Desktop/SPECIALE/detection_models/detection_models/pipeline_embeddings.py", line 62, in <module>
    create_and_fuse_db(db_name,"subtraction", rec_model=rec_model)
  File "/zhome/6c/3/121122/Desktop/SPECIALE/detection_models/detection_models/pipeline_embeddings.py", line 22, in create_and_fuse_db
    create_embeddings_from_db(db_name,
  File "/zhome/6c/3/121122/Desktop/SPECIALE/detection_models/detection_models/MY_FR/data_prep/create_emb__new.py", line 48, in create_embeddings_from_db
    save_folder_embeddings(emb_dir, orig_dir, app)
  File "/zhome/6c/3/121122/Desktop/SPECIALE/detection_models/detection_models/MY_FR/data_prep/create_emb__new.py", line 66, in save_folder_embeddings
    emb = app.get_embedding(img)
  File "/zhome/6c/3/121122/Desktop/SPECIALE/detection_models/detection_models/MY_FR/face_embedding.py", line 46, in get_embedding
    return self.models['recognition'].get_embedding(aligned_imgs)[0]
  File "/zhome/6c/3/121122/Desktop/SPECIALE/detection_models/detection_models/MY_FR/recognition/face_recognition.py", line 34, in get_embedding
    return self.model.get_embedding(imgs)
  File "/zhome/6c/3/121122/Desktop/SPECIALE/detection_models/detection_models/MY_FR/recognition/arcface_onnx.py", line 61, in get_embedding
    net_out = self.session.run(self.output_names, {self.input_name: blob})[0]
  File "/zhome/6c/3/121122/Desktop/SPECIALE/detection_models/env/MI/lib/python3.9/site-packages/onnxruntime/capi/onnxruntime_inference_collection.py", line 200, in run
    return self._sess.run(output_names, input_feed, run_options)
onnxruntime.capi.onnxruntime_pybind11_state.InvalidArgument: [ONNXRuntimeError] : 2 : INVALID_ARGUMENT : Got invalid dimensions for input: data for the following indices
 index: 0 Got: 2 Expected: 1
 Please fix either the inputs or the model.
```

the last lines of the output of that run are 
```out
Extracting embedding from /work3/s166154/Data/Original/UNCW/Album2/328957_00F16.JPG
[123.69997 129.58221 336.875   391.24542]
[357.62225   63.625374 381.36127   90.351036]
```

### First try to solution 

To look into the problem i will try to create an embedding only for the image : 328957_00F16
Note we know that 
- id:          328957
- gender: female

I am running from the interactive node, i.e. voltash 
and initalizing the environment by running 
```bash
source ../env/MI/bin/activate
module load cuda/11.6
module load cudnn/v8.4.1.50-prod-cuda-11.X
module load nccl/2.12.12-1-cuda-11.6

export OMP_NUM_THREADS=4
export OMP_PROC_BIND=false

python3 -m pip install --upgrade protobuf
```