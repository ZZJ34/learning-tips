## Burrow-Wheeler Aligner（BWA） for short-read alignment

BWA是一个软件包，是根据一个大规模的参考基因组（如人类基因组）比对 DNA 序列的工具。

BWA软件包包含了三种算法：

**BWA-backtrack**：适用于短序列长度最长为100bp的序列。

**BWA-SW**：适用于短序列长度为70bp到Mbp的序列。

**BWA-MEM**：同样适用于短序列长度为70bp到Mbp的序列。相对其他两种算法，其性能更佳，准确率更好。

🤔现在似乎他们都已经过时了，有新的算法提出来了。例如：[BWA-MEM2](https://github.com/bwa-mem2/bwa-mem2) 和 **[minimap2](https://github.com/lh3/minimap2)** 。

-------------

源代码网址：https://github.com/lh3/bwa

预编译工具包网址（bwakit）：https://sourceforge.net/projects/bio-bwa/files/bwakit/

BWA 主页：http://bio-bwa.sourceforge.net/bwa.shtml

👋**首先要说明的地方：**

- **对于完整的比对流程来说，还要依赖两个相关的工具即 [samtools](http://samtools.sourceforge.net/) 用于操作 sam 和 bam 文件的工具合集以及 seqtk 用于对测试数据进行预处理工具**。

- ⚠️**预编译工具包**（bwakit）包含了编译好的算法以及相关工具，可以直接使用。

- ⚠️**源代码**仅仅包含了算法代码，需要手动编译（必要的话可以创建环境变量，方便使用）。

- ⚠️**相关工具**大部分以源代码给出，需要手动编译（必要的话可以创建环境变量，方便使用）。

- 😓源代码中包含了一个 **bwakit** 文件，这个文件并不等于预编译好的工具包，**没有办法使用**，仅可参考的其中的 **README** 文档。

- 此外，还需要了解相关后缀文件的作用：

  `XXXX.fa/fasta`参考序列文件，[参考网址](https://baike.baidu.com/item/fasta%E6%A0%BC%E5%BC%8F/1168511?fr=aladdin)

  `XXXX.fq/fastq`待比对序列文件，[参考网址](https://baike.baidu.com/item/fastQ%E6%A0%BC%E5%BC%8F)

  `XXXX.sam/bam`比对结果，包含了各种比对结果信息的文件（CIGAR串等），🔎详细参考文献：**The Sequence Alignment/Map format and SAMtools**

👋在源代码网址的 README 中，也附上了相关三种算法的参考文献。

------

### **测试数据的问题**

待比对序列：[NCBI(National Center for Biotechnology Information)](https://www.ncbi.nlm.nih.gov/)

参考基因组：[UCSC Genome Browser](http://genome.ucsc.edu/)

😅当然，也可以自己随机生成符合格式规范的`fasta/fastq`的文件。

😅我自己并没有⏬下载到可以用的待比对序列，参考基因组的数据倒是有很多。实际测试 bwa 的时候，还是使用的我自己随机生成的 `fasta/fastq`的文件（有点尴尬......）。

------

### 使用流程

参考源[代码网址](https://github.com/lh3/bwa)或者这篇[博客](https://www.jianshu.com/p/19f58a07e6f4)

对于 BWA-backtrack 算法，其比对过程分为两步:

- 首先`bwa aln`生成`XXX.sai`文件即匹配的位置 => *SA(I)*
- 然后`bwas amse/sampe`生成最终的匹配结果`XXX.sam`

三种算法最终的比对结果可以通过 samtools 工具查看

