given zip file contains a zip file and a part of the image
which was made using script

now  we get a bunch of image from 0..3967
for i in {0..3967}
do
        j=$((i/64))
        k=$((i%64))

        if [ "$j" -lt "10" ];
        then
                j=0$((j))
        fi

        if [ "$k" -lt "10" ];
        then
                k=0$((k))
        fi


        mv result$i.png flag_$j\_$k.png
done

using this script we can make these image in 64*64 form

montage -mode concatenate -tile 64x64 flag_*.png out.png

now out.png has the binary
convert them to ascii text and got the flag
