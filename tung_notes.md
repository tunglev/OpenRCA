Run on WSL. The project should be stored in WSL disk rather than Window disk for speed (there is one security regression test for this).


numpy missmatch error first time running evaluate. Fix:

```
pip install "numpy<2"
```



After model configuration, a one-question smoke test is:

python -m rca.run_agent_standard \
  --dataset Bank \
  --start_idx 0 \
  --end_idx 0 \
  --sample_num 1 \
  --tag baseline-check



A full run over the four existing dataset groups is:
python -m rca.run_agent_standard \
  --auto True \
  --start_idx 0 \
  --end_idx 150 \
  --sample_num 1 \
  --controller_max_step 25 \
  --timeout 600 \
  --tag baseline-repro