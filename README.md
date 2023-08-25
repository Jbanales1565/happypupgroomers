Hadamard Matrix (2x2):
H = 1/sqrt(2) * [1 1; 1 -1];

Pauli X Matrix (2x2):
PauliX = [0 1; 1 0];


Identity Matrix (Any Size):
n = 3; % Size of the identity matrix
I = eye(n);


Rotation Matrix (2x2):
theta = pi/4; % Angle of rotation
R = [cos(theta) -sin(theta); sin(theta) cos(theta)];

Discrete Fourier Transform (DFT) Matrix (4x4):
N = 4; % Size of the DFT matrix
omega = exp(-2i*pi/N);
DFT = zeros(N);

for n = 0:N-1
    for k = 0:N-1
        DFT(n+1, k+1) = omega^(n*k);
    end
end

DFT = 1/sqrt(N) * DFT;
