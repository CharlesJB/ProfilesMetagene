URL_ENCODE=https://www.encodeproject.org/

DIR_EXTDATA=../inst/extdata
TARGETS_DOWNLOAD+=$(DIR_EXTDATA)/H3K4me1.bam
TARGETS_DOWNLOAD+=$(DIR_EXTDATA)/H3K27ac.bam

DIR_SRC=../src
SAMTOOLS=$(DIR_SRC)/samtools-1.2/samtools

TARGETS_INDEX=$(addsuffix .bai, $(TARGETS_DOWNLOAD))

.PHONY: all

all: download samtools index

download: $(TARGETS_DOWNLOAD)

samtools: $(TARGET_SAMTOOLS)

index: $(TARGETS_INDEX)

%.bam.bai: %.bam $(SAMTOOLS)
	$(SAMTOOLS) index $<

$(SAMTOOLS):
	make -C $(dir $@) all

$(DIR_EXTDATA)/H3K4me1.bam:
	wget -O $@ $(URL_ENCODE)/files/ENCFF000ARY/@@download/ENCFF000ARY.bam

$(DIR_EXTDATA)/H3K27ac.bam:
	wget -O $@ $(URL_ENCODE)/files/ENCFF000ASG/@@download/ENCFF000ASG.bam
