```fish
pip3 install --upgrade openai
openai tools fine_tunes.prepare_data -f training.jsonl -q # already done, only need to run on a new training set
openai api fine_tunes.create -m davinci --n_epochs 2 -t rtx.jsonl
openai api fine_tunes.follow -i ft-0Rc13SNcoxll45xumIwJl7pr # monitor progress. usually queued. takes about 10-15 minutes

openai api completions.create -m davinci:ft-kinchaku-2023-04-16-13-34-50 -p "How big is the GeForce RTX 4080 in terms of slots? Answer ->" -t 0
```