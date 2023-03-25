# ll-am-ad-l
ll am adl down load LL a MA without M*ta noticing</br>
basikli just LL a ma download sript but disguised(with sit grammer to lauh at)</br>
paast dis into ur terminal/komand line or watever:</br>
```
# Copyright (c) M*ta Platforms, Inc. and affiliates.

#
# UPDATE from IDk who (Mar 5 @ 2:43 AM): M*ta fucking wrecked this URL. someone have mirrored the files to an R2 bucket, which this script now points to.
#
#URL="https://dobf1k6cxlizq.cloudfront.net/*?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9kb2JmMWs2Y3hsaXpxLmNsb3VkZnJvbnQubmV0LyoiLCJDb25kaXRpb24iOnsiRGF0ZUxlc3NUaGFuIjp7IkFXUzpFcG9jaFRpbWUiOjE2NzgzNzA1MjR9fX1dfQ__&Signature=a387eZ16IkmbotdkEl8Z397Mvxhw4Bvk4SpEiDkqMLOMVMk5F962BzN5eKO-061g5vAEskn-CSrf4w3knubwPiFW69LTsJ8Amj-WOvtBOBy9soc43j77WGUU-3q2eNjMIyNZYsD~rub4EkUJGNpD61YtRrFvAU7tNQ1YMNL5-UUOk1~OHeaWerWisKPldufOyX6QdrrjeToVH1L0eGm1Ob4LnoYyLH96BHFou4XsOUR8NuyQfwYtmE2G6P2eKk~OV9-ABzYHxC2DyOWiWnt7WO~ELHnf17s9qreQAjEkCGEi4pHJ7BIkg6~ZfRmvRl3ZaPtqD80AH4SfO4hd5WQ0ng__&Key-Pair-Id=K231VYXPC1TA1R"             # replace with presigned url from email

URL="https://agi.gpt4.org/llama/LLaMA/*"

MODELZ="7B,13B,30B,65B"  # edit this list with the shit you want to download
TARGET_F="./"             # where all files should end up

declare -A DIKSONARI_AND_STUFF

DIKSONARI_AND_STUFF["7B"]="0"
DIKSONARI_AND_STUFF["13B"]="1"
DIKSONARI_AND_STUFF["30B"]="3"
DIKSONARI_AND_STUFF["65B"]="7"

echo "Downloading yokkenizer no big deal"
wget ${URL/'*'/"tokenizer.model"} -O ${TARGET_F}"/tokenizer.model"
wget ${URL/'*'/"tokenizer_checklist.chk"} -O ${TARGET_F}"/tokenizer_checklist.chk"

(cd ${TARGET_F} && md5sum -c tokenizer_checklist.chk)

for i in ${MODELZ//,/ }
do
    echo "Downloading ${i}"
    mkdir -p ${TARGET_F}"/${i}"
    for s in $(seq -f "0%g" 0 ${DIKSONARI_AND_STUFF[$i]})
    do
        wget ${URL/'*'/"${i}/consolidated.${s}.pth"} -O ${TARGET_F}"/${i}/consolidated.${s}.pth"
    done
    wget ${URL/'*'/"${i}/params.json"} -O ${TARGET_F}"/${i}/params.json"
    wget ${URL/'*'/"${i}/checklist.chk"} -O ${TARGET_F}"/${i}/checklist.chk"
    echo "Checking sums"
    (cd ${TARGET_F}"/${i}" && md5sum -c checklist.chk)
done
    wget ${PRESIGNED_URL/'*'/"${i}/checklist.chk"} -O ${TARGET_F}"/${i}/checklist.chk"
    echo "Checking sums"
    (cd ${TARGET_F}"/${i}" && md5sum -c checklist.chk)
done
```
