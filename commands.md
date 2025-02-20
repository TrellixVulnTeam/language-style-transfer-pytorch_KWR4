* Training:
```
nohup python code/style_transfer.py \
--saves_path ./model_saves/ \
--train ./data/yelp/sentiment.train \
--max_epochs 20 \
--vocab ./tmp/yelp.vocab \
--output ./tmp/sentiment.dev --max_train_size 176787 &> nohup1.out &
```


* Training:
```
nohup python code_bow/style_transfer.py \
--saves_path ./model_saves/ \
--train ./data/yelp/sentiment.train \
--max_epochs 20 \
--vocab ./tmp/yelp.vocab \
--output ./tmp/sentiment.dev &> nohup2.out &
```

```
nohup python code_bow/style_transfer.py \
 --saves_path ./model_saves/ \
 --train ./data/yelp/sentiment.train \
 --max_epochs 20 \
 --vocab ./tmp/yelp.vocab &> nohup_yelp_full_training.out &
```

* Testng:
```
nohup python code/style_transfer.py \
--test data/yelp/sentiment.test \
--vocab ./tmp/yelp.vocab
--model_path model_saves/model_0.0005_20_Mar-29-2020_09-13-10/20_epochs \
&> nohup2.out &
```

```
nohup python code/style_transfer.py --saves_path ./model_saves/ \
--train ./data/twitter/tweets.train --max_epochs 20 --vocab ./tmp/twitter.vocab \
--output ./tmp/twitter.dev &> nohup.out &
```

```
python code/style_transfer.py \
--test data/twitter/tweets.test \
--model_path model_saves/model_0.0005_100_Apr-01-2020_22-10-19/100_epochs \
--vocab ./tmp/twitter.vocab 
```

* Predicting

python code/style_transfer.py \
--predict "the service was great ." \
--vocab ./tmp/yelp.vocab \
--model_path model_saves/model_0.0005_100_Apr-01-2020_22-10-19/100_epochs 

* TextCNN testing:
```
python code/textcnn/main.py \
-test="model_saves/model_0.0005_20_Apr-02-2020_11-42-24/test_outputs_pos_to_neg,model_saves/model_0.0005_20_Apr-02-2020_11-42-24/test_outputs_neg_to_pos" \
-snapshot=snapshot/2020-03-26_14-01-27/best_steps_29400.pt
```

* BPE model training:
```
nohup python code/style_transfer.py \
--train /data/madhu/tweet_pairs_follower_1000_retweet_diff_50_without_url.csv.gz \
--cuda_device 2 \
--max_epochs 20 \
--epochs_per_checkpoint 5 \
--pretrain_flag True \
--autoencoder_pretrain_flag False \
&> nohup1.out &
```


* BOW training for IMDB dataset
```
python code_bow/style_transfer.py --saves_path ./model_saves/ --train /data/madhu/imdb_dataset/processed_data/cross_alignment/reviews.train --max_epochs 20 --vocab ./tmp/imdb.vocab --max_train_size 500 --batch_size 8 --cuda_device 2
```
