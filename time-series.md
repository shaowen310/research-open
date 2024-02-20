# Time Series

## PatchTST

```python
def forward(self, x) -> Tensor:
        # x: [bs, nvars, patch_len, patch_num]
        # we may consider patch_len as seq_len
        
        n_vars = x.shape[1]                                                                          
                                                                                          
        # Input encoding
        x = x.permute(0,1,3,2) # [bs, nvars, patch_num, patch_len]
        x = self.W_P(x) # [bs, nvars, patch_num, d_model]

        u = torch.reshape(x, (x.shape[0]*x.shape[1],x.shape[2],x.shape[3]))
        # u: [bs * nvars, patch_num, d_model]
        u = self.dropout(u + self.W_pos)
        # u: [bs * nvars, patch_num, d_model]

        # Encoder
        z = self.encoder(u) # [bs * nvars, patch_num, d_model]
        z = torch.reshape(z, (-1,n_vars,z.shape[-2],z.shape[-1]))                
        # z: [bs, nvars, patch_num, d_model]
        z = z.permute(0,1,3,2) # [bs, nvars, d_model, patch_num]
        
        return z    
```
