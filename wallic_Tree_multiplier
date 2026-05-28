module wallic_Tree_multiplier(
    prod,
    a,
    b
    );
    input [3:0] a,b;
    output [7:0]prod;
    
    wire s0,s1,s2,s3,s4,s5,s6,s7,s8,s9,s10,s11;
    wire c0,c1,c2,c3,c4,c5,c6,c7,c8,c9,c10,c11;
    
    wire p[3:0][3:0];
    genvar i;
    genvar j;
    
//    reg p[3:0][3:0];
//    integer i;
//    integer j;

 generate
      for(i=0;i<4;i=i+1)
       begin
        for(j=0;j<4;j=j+1)
        begin
         assign p[i][j] = a[j] &b[i];
        end  
     end
 endgenerate
   

 //stage 1
half_adder HA1(s0,c0,p[1][0],p[0][1]);
full_adder FA1(s1,c1,p[0][2],p[1][1],p[2][0]);
full_adder FA2(s2,c2, p[0][3],p[1][2],p[2][1]);
full_adder FA3(s3,c3,p[1][3],p[2][2],1'b0);

//stage 2
full_adder FA4(s4,c4,c0,s1,1'b0);
full_adder FA5(s5,c5,s2,c1,p[3][0]);
full_adder FA6(s6,c6,s3,c2,p[3][1]);
full_adder FA7(s7,c7,p[2][3],c3,p[3][2]);

//stage 3
full_adder FA8(s8,c8,c4,s5,1'b0);
full_adder FA9(s9,c9,c5,s6,c8);
full_adder FA10(s10,c10,s7,c6,c9);
full_adder FA11(s11,c11,c7,p[3][3],c10);


assign prod[0]= p[0][0];
assign prod[1]= s0;
assign prod[2]= s4;
assign prod[3]= s8;
assign prod[4]= s9;
assign prod[5]= s10;
assign prod[6]= s11;
assign prod[7]= c11;

endmodule

