## Codignitor Crude Operation

### Controller file code

```
	public function index()
	{
		$qry=$this->db->get('admin');
		$ar['data']=$qry->result_array();
		if ($this->input->post()) {
			$row['name']=$this->input->post('name');
			$row['email']=$this->input->post('email');
			$row['password']=$this->input->post('password');
			$this->db->insert('admin',$row);
			redirect();
		}
		$this->load->view('welcome_message',$ar);
	}
	public function update($id='')
	{

		$this->db->where('id',$id);
		$qry=$this->db->get('admin');
		$ar['row']=$qry->row_array();
		if ($this->input->post()) {
			$row['name']=$this->input->post('name');
			$row['email']=$this->input->post('email');
			$row['password']=$this->input->post('password');
			$this->db->where('id',$id);
			$this->db->update('admin',$row);
			redirect();
		}
		$this->load->view('welcome_message',$ar);
	}
	public function delete($id='')
	{
		$this->db->where('id',$id);
		$qry=$this->db->delete('admin');
		redirect();
	}

```
### View file code

```
  <form method="post">
			name :<input type="text" name="name" value="<?php echo @$row['name']?>">
      email :<input type="text" name="email" value="<?php echo @$row['email']?>">
      password :<input type="text" name="password" value="<?php echo @$row['password']?>">
      <input type="submit" name="save">
	</form>
	<?php if(@$data){?>
	<table border="1">
		<tr>
			<td>NAME</td>
			<td>EMAAIL</td>
			<td>Action</td>
		</tr>
		<?php foreach($data as $row){?>
			<tr>
				<td><?php echo $row["name"];?></td>
				<td><?php echo $row["email"];?></td>
				<td><a href="<?php echo site_url('Welcome/update/'.$row['id']);?>">Update</a></td>
				<td><a href="<?php echo site_url('Welcome/delete/'.$row['id']);?>">Delete</a></td>
			</tr>
		<?php }?>
	</table>
	<?php }?>
```


