# sa_stra 正负样本比例调整
sa_stra<-function(data,flag,freq){
	set.seed(1)
	n_p1=sum(flag)
	p1=subset(data,flag==1)
	p0=subset(data,flag==0)
	n_p2=floor(((1-freq)*n_p1)/(freq))
    index=sample(nrow(p0),n_p2)
    p2=p0[index,]
    new_data=rbind(p1,p2)
    return(new_data)
}
