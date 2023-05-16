# Form_onChange_onClick_event

import React, { useState } from "react";
import "./App.css";
import { spacing } from "@mui/system";
import Button from '@mui/material/Button';
import Box from '@mui/material/Box';

import {
  FormControl,
  Grid,
  InputLabel,
  MenuItem,
  Select,
  TextField,
  Typography,
} from "@mui/material";

function App() {
  const [data, setData] = useState({});
  const handleData = () => {
    console.log("Data is shown below: ", data);
  };
  const onChange = (e) => {
    debugger;
    setData((prevData) => {
      prevData[e.target.name] = e.target.value;
      return { ...prevData };
    });
  };
  return (
    // <TextField variant = "outlined"></TextField>
    <>
      {/* <Typography>{data.Name}</Typography> */}
      <h2>My Details</h2>
      <Grid container spacing={6}>
        <Grid item xl={6} md={6} sm={6} xs={6}>
          <TextField
            id="standard-basic"
            label="Name"
            variant="outlined"
            value={data.name}
            name="Name"
            onChange={onChange}
            margin="normal"
            color="success"
          />
        </Grid>
        <Grid item xl={6} md={6} sm={6} xs={6} size="medium">
          <InputLabel
            id="demo-simple-select-label"
            size={{ m: 1, minWidth: 120 }}
          >
            Gender
          </InputLabel>
          <Select
            labelId="demo-simple-select-label"
            id="demo-simple-select"
            name="Gender"
            label="Choose your gender"
            onChange={onChange}
            color="success"
          >
            <MenuItem value={"Male"} name="Gender" onChange={onChange}>
              Male
            </MenuItem>
            <MenuItem value={"Female"} name="Gender">
              Female
            </MenuItem>
            <MenuItem value={"Others"} name="Gender">
              Others
            </MenuItem>
          </Select>
        </Grid>
        <Grid item xl={6} md={6} sm={6} xs={6}>
          <TextField
            id="standard-basic"
            label="EmailId"
            variant="outlined"
            name="EmailId"
            value={data.EmailId}
            onChange={onChange}
            required
            color="success"
          />
        </Grid>
        <Grid item xl={6} md={6} sm={6} xs={6}>
          <TextField
            id="standard-basic"
            label="Nationality"
            variant="standard"
            name="Nationality"
            onChange={onChange}
            required
            color="success"
          />
        </Grid>
        <Grid item xl={6} md={6} sm={6} xs={6}>
          <InputLabel id="demo-simple-select-label" color="success">
            Age
          </InputLabel>
          <Select
            labelId="demo-simple-select-label"
            id="demo-simple-select"
            name="age"
            label="Age"
            // value={age}
            onChange={onChange}
            color="success"
          >
            <MenuItem value={10}>Ten</MenuItem>
            <MenuItem value={20}>Twenty</MenuItem>
            <MenuItem value={30}>Thirty</MenuItem>
          </Select>
        </Grid>
        <Grid item xl={6} md={6} sm={6} xs={6}>
          <TextField
            id="standard-basic"
            label="Phone No."
            variant="outlined"
            name="Phone"
            value={data.phone}
            onChange={onChange}
            required
            color="success"
          />
        </Grid>
        <Grid item xl={6} md={6} sm={6} xs={6}>
          <Typography align="auto">
          <Button id="btn" onClick={handleData} variant="outlined">
            Click Here
          </Button>
          </Typography>
        </Grid>
      </Grid>
    </>
  );
}

export default App;
