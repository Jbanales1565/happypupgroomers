% Check if the product is close enough to the identity matrix
is_unitary = max(max(abs(product - eye(size(A))))) < tolerance;

% Check if the product of the conjugate transpose is close enough to the identity matrix
is_unitary_conj = max(max(abs(product_conj - eye(size(A))))) < tolerance;

% Combine both checks to determine if A is unitary
is_unitary_final = is_unitary && is_unitary_conj;

if is_unitary_final
    disp('The matrix is unitary.');
else
    disp('The matrix is not unitary.');
end
