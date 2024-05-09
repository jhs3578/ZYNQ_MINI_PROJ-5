full project 
-vivado version 2022.2
https://drive.google.com/file/d/1RbWCRLt-h-EnT48WaYq9c5Vw1IGkd_3x/view?usp=sharing

ILA IP에서 probe 7개 만들어서 디버깅해 봤습니다.

아래는 ILA IP 를 인스턴스 한 코드입니다.

wire [0:0] ila_probe0;
wire [0:0] ila_probe1;
wire [3:0] ila_probe2;
wire [4:0] ila_probe3;
wire [0:0] ila_probe4;
wire [0:0] ila_probe5;
wire [6:0] ila_probe6;

ila_0 ila_0_inst
(
.clk(clk),

.probe0(ila_probe0), // input wire [0:0]  probe0  
.probe1(ila_probe1), // input wire [0:0]  probe1 
.probe2(ila_probe2), // input wire [3:0]  probe2 
.probe3(ila_probe3), // input wire [4:0]  probe3 
.probe4(ila_probe4), // input wire [0:0]  probe4 
.probe5(ila_probe5), // input wire [0:0]  probe5 
.probe6(ila_probe6)  // input wire [6:0]  probe6
);
assign ila_probe0[0:0] =SCL;
assign ila_probe1[0:0] =SDA;   
assign ila_probe2[3:0] =LED_STATE[3:0];   
assign ila_probe3[4:0] =state[4:0];   
assign ila_probe4[0:0] =write_start_flag_wire;
assign ila_probe5[0:0] =read_start_flag_wire;
assign ila_probe6[6:0] =cnt[6:0];  
