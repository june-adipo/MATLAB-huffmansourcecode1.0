x=input('enter the number of symbol: ');
N=1:x;
disp('the number of symbols are N');
disp(N);
p=input('enter the probabilities=');
disp('the probabilities are: ');
disp(p);
S=sort(p,'descend');
disp('the sorted probabilities are:');
disp(S);
[dict,avglen]=huffmandict(N,S);
disp('the average length of the code is:');
disp(avglen);
H=0;
for i=1:x
    H=H+(p(i)*log2(1/p(i)));
end
disp('Entropy is:');
disp(H);
disp('bits/msg');
E=(H/avglen)*100;
disp('Efficiency is:');
disp(E);
codeword=huffmanenco(N,dict);
disp('the codewords are:');
disp(codeword);
decode=huffmandeco(codeword,dict);
disp('Decoded output is:');
disp(decode);


