SR_flipflop
AIM:

To implement SR flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

Truth Table:

<img width="571" height="376" alt="image" src="https://github.com/user-attachments/assets/17e5b757-75d1-4eb6-a923-d77ea5b7cfae" />


RTL Image:

[RTL Viewer.pdf](https://github.com/user-attachments/files/24171278/RTL.Viewer.pdf)

Waveimage:

[wave.pdf](https://github.com/user-attachments/files/24171302/wave.pdf)


Register Number: 25017522

Name: Karthi V

program:
```
module SRflipflop(
    input  wire clk, rst, S, R,
    output reg  Q
);
    always @(posedge clk) begin
        if (rst)
            Q <= 1'b0;         // Reset
        else begin
            case ({S,R})
                2'b00: Q <= Q;     // No change
                2'b01: Q <= 1'b0;  // Reset
                2'b10: Q <= 1'b1;  // Set
                2'b11: Q <= 1'bx;  // Invalid
            endcase
        end
    end
endmodule
```


Result :

we got the expected output in Quatras , and the model sim
